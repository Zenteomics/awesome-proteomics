---
title: "Label-Free DDA Proteomics - End-to-End Workflow"
status: current
author: "@eneskemalergin"
last_reviewed: 2026-09-27
tags: [workflow, dda, label-free, lfq, nextflow, quantms, msstats]
---

# Label-Free DDA Proteomics - End-to-End Workflow

**TL;DR:** Use [quantms](../README.md#cloud--hpc) for identification, label-free quantification, and quality control, then [MSstats](../README.md#statistical-analysis) for differential abundance. This example pins quantms 1.10.0. That release publishes QPX data and MSstats input tables; statistical analysis is a separate R step.

## Who this is for

You have bottom-up, label-free DDA data and want to compare protein abundance between conditions. The worked example assumes six Thermo raw files from independent biological samples: three controls and three cases. Read the [Beginner's Guide](../guides/beginners-guide.md) for acquisition types and file formats.

## The pipeline at a glance

```text
Thermo raw files + SDRF metadata + target FASTA
    -> conversion to mzML
    -> database search, rescoring, and FDR filtering
    -> protein inference and label-free quantification
    -> QPX dataset + MSstats input CSV + pMultiQC report
    -> separate MSstats analysis in R
    -> differential-abundance table
```

quantms is described in [Dai et al. (2024)](https://doi.org/10.1038/s41592-024-02343-1). Commands and outputs below follow the [1.10.0 release](https://github.com/bigbio/quantms/releases/tag/1.10.0).

## Worked example: a quantms DDA-LFQ run

### Step 0 - Prerequisites

Use Linux, macOS, or WSL with Docker available to your user. quantms 1.10.0 requires Nextflow 25.10.4 or later; this example pins Nextflow 26.04.6. Current Nextflow requires Java 17 through 26. See the [quantms release configuration](https://github.com/bigbio/quantms/blob/1.10.0/nextflow.config) and [Nextflow installation instructions](https://docs.seqera.io/nextflow/install).

Download the standalone Nextflow executable into your analysis directory:

```bash
curl -fL https://github.com/nextflow-io/nextflow/releases/download/v26.04.6/nextflow-26.04.6-dist -o nextflow
chmod +x nextflow
java -version
./nextflow -version
docker info
```

Use `-profile singularity` or `-profile podman` if that is your configured container runtime. quantms no longer offers a Conda execution profile.

### Step 1 - Smoke test before real data

Run the bundled BSA test to check downloads, containers, and execution:

```bash
./nextflow run bigbio/quantms -r 1.10.0 \
    -profile test,docker \
    --outdir test_results/
```

The [test profile](https://github.com/bigbio/quantms/blob/1.10.0/conf/tests/test_lfq.config) limits each process to four CPUs and 12 GB RAM. Allow time and disk space for the first container downloads. Its permissive FDR settings and decoy quantification are for software testing; use the analysis settings in Step 4 for your experiment.

### Step 2 - Describe the experiment (SDRF)

Download the [six-sample SDRF example](examples/label-free-dda.sdrf.tsv) and save it as `experiment.sdrf.tsv` in your analysis directory. Put `control_1.raw` through `control_3.raw` and `treated_1.raw` through `treated_3.raw` in a `raw/` subdirectory.

The template has one row per run, unique biological replicate identifiers, two disease conditions, file locations, and acquisition parameters. It assumes Q Exactive HCD data, trypsin digestion, fixed carbamidomethylation of cysteine, variable methionine oxidation, and 5 ppm precursor / 0.03 Da fragment tolerances. Replace these values and the sample descriptions with your actual experiment. Fill in tissue and cell type where known.

Validate with the same SDRF parser image used by this quantms release:

```bash
docker run --rm -v "$PWD":/data -w /data \
    quay.io/biocontainers/sdrf-pipelines:0.0.33--pyhdfd78af_0 \
    parse_sdrf validate-sdrf --sdrf_file experiment.sdrf.tsv
```

quantms also checks metadata when it starts. The input must be SDRF; the older OpenMS experimental-design input is no longer accepted. See the [SDRF specification](https://github.com/bigbio/proteomics-sample-metadata/blob/master/sdrf-proteomics/README.adoc) for other experimental designs.

### Step 3 - Get the protein database

Save the appropriate [UniProt](../README.md#sequence--function-knowledge-bases) protein sequences, including relevant contaminants, as `uniprot_human.fasta`. Record the proteome release and download date.

Use a target-only FASTA with the command below. quantms 1.10.0 defaults to `add_decoys = false`, so this example explicitly passes `--add_decoys`. If your FASTA already contains decoys, omit that flag and configure the matching decoy prefix.

### Step 4 - Run the full workflow

```bash
./nextflow run bigbio/quantms -r 1.10.0 \
    -profile docker \
    --input experiment.sdrf.tsv \
    --root_folder "$PWD/raw" \
    --local_input_type raw \
    --database uniprot_human.fasta \
    --add_decoys \
    --search_engines comet,msgf \
    --protein_level_fdr_cutoff 0.01 \
    --psm_level_fdr_cutoff 0.01 \
    --outdir results/ \
    -resume
```

`--root_folder` locates your local files, and `--local_input_type raw` preserves their Thermo extension. Search parameters in the SDRF take precedence over corresponding command-line defaults. `-resume` reuses unchanged completed tasks; retain the `work/` and `.nextflow/` directories to use it.

The [release parameter schema](https://raw.githubusercontent.com/bigbio/quantms/1.10.0/nextflow_schema.json) documents these options. For centroided mzML input, update the file names and use `--local_input_type mzML`.

### Step 5 - Inspect the outputs

According to the [1.10.0 output documentation](https://github.com/bigbio/quantms/blob/1.10.0/docs/output.md), the files to keep include:

- `results/qpx/`: identification and quantification data in Parquet tables and a MuData container.
- `results/quant_tables/*_msstats_in.csv`: feature quantities and sample annotations for MSstats.
- `results/pmultiqc/`: quality-control reports.
- `results/pipeline_info/`: execution reports, parameters, and software versions.

Review identification rates, intensity distributions, missing values, and agreement among replicates before testing biological differences. This release replaces the published mzTab quantification output with QPX and does not run MSstats post-processing.

### Step 6 - Run statistics separately

Install [MSstats](https://bioconductor.org/packages/MSstats) and [MSstatsConvert](https://bioconductor.org/packages/MSstatsConvert) in R:

```r
if (!requireNamespace("BiocManager", quietly = TRUE)) {
    install.packages("BiocManager")
}
BiocManager::install(c("MSstats", "MSstatsConvert"), ask = FALSE, update = FALSE)
```

Run this from your analysis directory after quantms finishes:

```r
reports <- list.files(
    "results/quant_tables",
    pattern = "_msstats_in[.]csv$",
    full.names = TRUE
)
stopifnot(length(reports) == 1L)

raw <- read.csv(reports[[1]], check.names = FALSE)
input <- MSstatsConvert::OpenMStoMSstatsFormat(raw)
processed <- MSstats::dataProcess(
    input, normalization = "equalizeMedians", MBimpute = FALSE
)
comparison <- MSstats::groupComparison(
    contrast.matrix = "pairwise", data = processed
)
write.csv(
    comparison$ComparisonResult,
    "results/differential-abundance.csv",
    row.names = FALSE
)
writeLines(
    capture.output(sessionInfo()),
    "results/msstats-session-info.txt"
)
```

This uses the [OpenMS converter](https://github.com/Vitek-Lab/MSstatsConvert/blob/devel/R/converters_OpenMStoMSstatsFormat.R) and the [MSstats analysis functions](https://github.com/Vitek-Lab/MSstats#quick-start). It compares all condition pairs and saves package versions. Check the comparison labels before interpreting fold-change direction.

Median normalization assumes most proteins do not change systematically. This example leaves missing-value imputation off; choose normalization, missing-value handling, and contrasts to match your experiment. Inspect the converted `Condition`, `BioReplicate`, and `Run` columns before fitting the model. Repeated measures and paired designs need their own annotation.

## Validation

Checked on: 2026-09-27. The SDRF example passes validation and OpenMS conversion with sdrf-pipelines 0.0.33, with no conversion warnings. The R analysis runs on MSstatsConvert's bundled OpenMS example using MSstats 4.20.0 and MSstatsConvert 1.22.1.

The quantms 1.10.0 BSA smoke test, run with Nextflow 26.04.6 and Podman, completed metadata parsing and database searching. It stopped while unpacking the rescoring container because temporary storage exceeded its quota. Full quantification and the subsequent analysis of those outputs have not been verified in this review.

## Alternatives

- [FragPipe](../README.md#discovery-proteomics): use its LFQ-MBR workflow for a desktop route, then analyze the exported quantities with a downstream statistics tool.
- [MaxQuant](../README.md#discovery-proteomics): identify and quantify with MaxQuant, then import its reports into MSstats.
- [Frag'n'Flow and snakemake-ms-proteomics](../README.md#cloud--hpc): see the list for other scripted workflows.

## Common pitfalls

- **Incorrect metadata:** technical repeats and fractions are not independent biological replicates.
- **Incorrect decoys:** add decoys exactly once and match the configured prefix to the database.
- **Assuming a fixed runtime:** downloads, search database size, run count, and hardware determine how long processing takes.
- **Treating test settings as analysis settings:** the bundled BSA test deliberately relaxes identification filters.
- **Skipping QC:** investigate unexpected missingness or replicate disagreement before interpreting differential abundance.

## Related

- [Beginner's Guide](../guides/beginners-guide.md)
- [File Format Cheat Sheet](../guides/file-format-cheat-sheet.md)
- [Tool Compatibility Matrix](../guides/compatibility-matrix.md)
- [Statistical Analysis tools](../README.md#statistical-analysis)

*This workflow describes one route for label-free DDA. For corrections, see [Writing a workflow](../CONTRIBUTING.md#writing-a-workflow).*
