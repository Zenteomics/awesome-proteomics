---
title: "Label-Free DDA Proteomics - End-to-End Workflow"
status: current
author: "@eneskemalergin"
last_reviewed: 2026-06-30
tags: [workflow, dda, label-free, lfq, nextflow, quantms, msstats]
---

# Label-Free DDA Proteomics - End-to-End Workflow

**TL;DR**
- Label-free DDA (data-dependent acquisition) is the most common entry point for shotgun proteomics: digest proteins, run LC-MS/MS, identify peptides against a sequence database, quantify from MS1 precursor intensity, then test for differential abundance.
- This page walks a *complete* run end to end with **quantms**, a reproducible, cloud-ready Nextflow pipeline (its DDA-LFQ branch). Every command below is real and runnable.
- The same conceptual steps apply if you prefer a desktop tool - FragPipe (LFQ-MBR) and MaxQuant + MSstats are covered as alternatives.
- Every pipeline is listed with its canonical source (repository + paper) so you can cite it and reproduce the analysis.

## Who this is for
You have label-free DDA data (or a public dataset) and want a defensible path from raw files to a ranked list of differentially abundant proteins, with quality control you can show a reviewer. If you are brand new, read the Beginner's Guide first; this page assumes you know what a peptide-spectrum match and an FDR cutoff are.

## The pipeline at a glance
Every label-free DDA analysis - regardless of tool - is the same backbone:

1. **Convert / read** vendor raw files (mzML is the open interchange format).
2. **Search** spectra against a protein FASTA to get peptide-spectrum matches (PSMs).
3. **Rescore + FDR-filter** PSMs (target-decoy), then infer proteins.
4. **Quantify** at MS1 precursor level (feature detection, retention-time alignment, feature linking).
5. **Normalize + test** for differential abundance.
6. **QC + visualize** the whole thing.

~~~text
raw files (.raw / .d / .mzML)
   -> ThermoRawFileParser / vendor conversion
peak lists (mzML)
   -> search engines (Comet, MSGF+, Sage)
PSMs -> rescoring (Percolator + MS2PIP / DeepLC) -> ConsensusID
   -> protein inference + picked-protein FDR
ProteomicsLFQ  (feature detection -> RT alignment -> feature linking -> quant)
   -> protein / peptide quantities (mzTab)
MSstats  (normalize -> impute -> linear mixed model)
   -> differential abundance + pmultiqc QC report + volcano / PCA / heatmap
~~~

## Worked example: a complete quantms DDA-LFQ run

quantms is the recommended modern default: it is peer-reviewed, nf-core-derived, SDRF-driven (so the run is self-documenting), and it scales from a laptop to AWS/GCP/Azure/HPC without changing the command. Source: github.com/bigbio/quantms ; docs docs.quantms.org ; Dai C, Pfeuffer J, Wang H, et al. *quantms: a cloud-based pipeline for quantitative proteomics enables the reanalysis of public proteomics data.* Nature Methods. 2024;21:1603-1607. DOI 10.1038/s41592-024-02343-1.

### Step 0 - Prerequisites
Nextflow (>= 23.04), Java 11+, and one container/environment engine (Docker, Singularity, or Conda).
~~~bash
curl -s https://get.nextflow.io | bash
./nextflow -version
~~~

### Step 1 - Smoke test before real data
Run the bundled test profile first. It pulls a tiny dataset and runs the entire DDA-LFQ chain in a few minutes - if this fails, fix the environment before touching your data.
~~~bash
nextflow run bigbio/quantms -profile test,docker --outdir test_results/
~~~

### Step 2 - Describe the experiment (SDRF)
quantms is driven by an SDRF-Proteomics file (one row per sample-to-raw-file relationship), carrying both sample metadata and MS parameters. This is what makes the run reproducible and submission-ready. A minimal two-condition design (3 control vs 3 treated, Thermo Q Exactive):
~~~text
source name	characteristics[organism]	characteristics[disease]	assay name	comment[data file]	comment[instrument]	comment[label]	comment[cleavage agent details]	factor value[disease]
sample 1	Homo sapiens	normal	run 1	control_1.raw	NT=Q Exactive;AC=MS:1001911	NT=label free sample;AC=MS:1002038	NT=Trypsin;AC=MS:1001251	normal
sample 2	Homo sapiens	normal	run 2	control_2.raw	NT=Q Exactive;AC=MS:1001911	NT=label free sample;AC=MS:1002038	NT=Trypsin;AC=MS:1001251	normal
sample 3	Homo sapiens	normal	run 3	control_3.raw	NT=Q Exactive;AC=MS:1001911	NT=label free sample;AC=MS:1002038	NT=Trypsin;AC=MS:1001251	normal
sample 4	Homo sapiens	carcinoma	run 4	treated_1.raw	NT=Q Exactive;AC=MS:1001911	NT=label free sample;AC=MS:1002038	NT=Trypsin;AC=MS:1001251	carcinoma
sample 5	Homo sapiens	carcinoma	run 5	treated_2.raw	NT=Q Exactive;AC=MS:1001911	NT=label free sample;AC=MS:1002038	NT=Trypsin;AC=MS:1001251	carcinoma
sample 6	Homo sapiens	carcinoma	run 6	treated_3.raw	NT=Q Exactive;AC=MS:1001911	NT=label free sample;AC=MS:1002038	NT=Trypsin;AC=MS:1001251	carcinoma
~~~
Validate it before running (this catches the mistakes that waste a cluster run):
~~~bash
pip install sdrf-pipelines
parse_sdrf validate-sdrf --sdrf_file experiment.sdrf.tsv
~~~
Not ready to write SDRF? quantms also accepts an OpenMS-style experimental-design TSV - see the BSA_design_urls.tsv example in github.com/bigbio/quantms-utils . The SDRF spec and a web editor live at sdrf.quantms.org .

### Step 3 - Get the protein database
Provide a target FASTA (for example, a reviewed human UniProt proteome). quantms generates and appends decoys internally for target-decoy FDR, so do not pre-add them.

### Step 4 - Run the full workflow
~~~bash
nextflow run bigbio/quantms \
    -profile docker \
    --input experiment.sdrf.tsv \
    --database uniprot_human.fasta \
    --search_engines comet,msgf \
    --protein_level_fdr_cutoff 0.01 \
    --outdir results/ \
    -resume
~~~
The -resume flag reuses cached steps so a re-run after a tweak does not start from zero. Use -profile singularity or -profile conda instead of docker to match your environment.

### Step 5 - What runs inside (and why it matters)
1. **SDRF parsing** - turns your annotation into per-file search parameters (sdrf-pipelines).
2. **Conversion** - vendor raw to mzML via ThermoRawFileParser (Bruker .d handled by the matching reader).
3. **Database search** - one or more engines (Comet, MSGF+, and Sage are supported); using more than one and combining them improves sensitivity.
4. **PSM rescoring** - Percolator (or a distribution-fitting PEP), optionally boosted by ML predictors (MS2PIP for fragment intensities, DeepLC for retention time); ConsensusID merges engines into one score.
5. **Protein inference + FDR** - Bayesian or aggregation inference, then picked-protein FDR filtering.
6. **ProteomicsLFQ** - MS1 feature detection, retention-time alignment across runs, feature linking, and protein quantification (MaxLFQ-style).
7. **MSstats** - normalization, imputation, and a linear mixed-effects model for differential abundance, with Benjamini-Hochberg p-value adjustment.
8. **pmultiqc** - one interactive HTML QC report for the whole run.

> Why bother with ML rescoring? On typical data MS2PIP/DeepLC rescoring lifts identifications by roughly 10-30% at the same FDR - free sensitivity for one flag.

### Step 6 - Outputs you actually use
- mzTab - identifications plus quantities in a single open file, ready for PRIDE submission.
- MSstats input CSV + MSstats-processed mzTab - the normalized/imputed quantities.
- Differential-abundance table - log2 fold-change and adjusted p-value per protein, straight into a volcano plot.
- pmultiqc report - ID rates, intensity distributions, RT consistency, and missing-value patterns at a glance.

### Step 7 - Stats and visualization
MSstats already runs in the pipeline, so you get the differential-abundance table for free. For custom figures, load the MSstats output into the MSstats R package (volcano, QC, and comparison plots) or use mokume (successor to ibaqpy) for absolute abundance (iBAQ). pmultiqc covers run-level QC. If you would rather click than code, the same quantms DDA-LFQ logic is available as a browser app (OpenMS/quantms-web).

### Sanity-check your result
Before trusting biology, confirm the quantification behaves. A standard template is a spike-in benchmark: the quantms paper recovers all 48 UPS1 proteins at high spike concentrations and cleanly separates them from the fixed E. coli background, with accuracy dropping only at the lowest concentrations (fewer IDs, noisier quant). Run a small spike-in or a technical-replicate pair through the same command and check that replicates cluster and known-stable proteins do not move.

## Recent Nextflow pipelines (with sources)
These are the actively relevant Nextflow options for DDA label-free, each with a citable source. (These also belong in the main README.)

| Pipeline | Scope | Status | Canonical source |
| --- | --- | --- | --- |
| quantms (bigbio/quantms) | DDA-LFQ + DDA-ISO (TMT/iTRAQ); DIA split to quantmsdiann | Active, recommended | repo github.com/bigbio/quantms ; docs docs.quantms.org ; Dai et al., Nat Methods 2024, 21:1603-1607, doi:10.1038/s41592-024-02343-1 |
| Frag'n'Flow | Nextflow wrapper around the FragPipe ecosystem for large-scale LFQ | New (Jan 2026) | BMC Bioinformatics 2026, doi:10.1186/s12859-025-06305-y |
| nf-core/proteomicslfq | OpenMS + MSstats LFQ | Predecessor to quantms (DSL1; legacy) | github.com/nf-core/proteomicslfq ; Zenodo 10.5281/zenodo.4106004 |
| nf-core/mhcquant (MHCquant2) | DDA immunopeptidomics (specialized, not general LFQ) | Active (3.x) | github.com/nf-core/mhcquant ; MHCquant2, PMC12455830 |
| nf-core/msproteomics | FragPipe-ecosystem pipeline | Proposed (Mar 2026) - one to watch | nf-core proposals issue #121 |

Context worth knowing: nf-core/quantms itself is **archived at 1.2.0**, with active development moved to bigbio/quantms, and the nf-core community now runs a Mass Spectrometry Proteomics Special Interest Group steering toward thin, modular, chainable DDA/DIA/TMT pipelines.

## Desktop alternatives (same backbone, different driver)
- **FragPipe (LFQ-MBR workflow)** - load the LFQ-MBR workflow: MSFragger search -> MSBooster + Percolator rescoring -> ProteinProphet (Philosopher) grouping -> IonQuant with FDR-controlled match-between-runs. Outputs combined_protein.tsv (Intensity, MaxLFQ, Spectral Count). Visualize with FragPipe-Analyst. Source: fragpipe.nesvilab.org ; IonQuant - Yu et al., Mol Cell Proteomics 2021, doi:10.1016/j.mcpro.2021.100077.
- **MaxQuant + MSstats** - the classic desktop route: MaxQuant for ID + LFQ intensities, then MSstats for statistics. The Galaxy Training Network has a full hands-on tutorial (MaxQuant + MSstats for label-free data, using the Foll et al. 2018 skin-cancer cohort): training.galaxyproject.org (Proteomics topic).

## Snakemake alternative
If your group standardizes on Snakemake rather than Nextflow: **MPUSP/snakemake-ms-proteomics** wraps FragPipe + MSstats with QC (v1.0.0, Jan 2025). Source: github.com/MPUSP/snakemake-ms-proteomics .

## Common pitfalls
- **Re-converting raw files.** Let the pipeline convert; do not feed it mzML that was already centroided or demultiplexed unless you know why.
- **Decoys added twice.** quantms adds decoys itself - supplying a target+decoy FASTA inflates or breaks FDR.
- **Too few replicates.** Differential abundance needs replication; 3 per condition is a practical floor, not a luxury.
- **Ignoring missing values.** Label-free DDA is missing-value heavy; check the pmultiqc missingness panel before interpreting fold-changes.
- **Skipping the smoke test.** The test profile catches most environment problems in minutes.

## A note on completeness
This is one well-trodden path, not the only correct one. It does not cover isobaric labeling (TMT/iTRAQ), DIA, targeted (PRM/SRM), or specialized branches (PTM-site localization, immunopeptidomics, single-cell), each of which has its own workflow page or guide. Tool choices here are defaults, not endorsements - read the cross-linked pages and pick what fits your data and constraints.

## Related
- Beginner's Guide - concepts and vocabulary (../guides/beginners-guide.md).
- File Format Cheat Sheet - what every extension is (../guides/file-format-cheat-sheet.md).
- Tool Compatibility Matrix - which tool reads which raw format, on which OS (../guides/compatibility-matrix.md).
- README sections: Quantitative Proteomics, Identification, Statistical Analysis, Bioinformatics & Computational Tools.

*This workflow reflects the author's experience as of the last reviewed date. Spot an error or something out of date? Open a [Discussion or update PR](../CONTRIBUTING.md#writing-a-guide) - workflows are meant to be refreshed. When experts genuinely disagree and cannot reconcile, we also welcome [competing guides](../GOVERNANCE.md#guide-disagreements).*
