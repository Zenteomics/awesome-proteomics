---
title: "Beginner's Guide to Proteomics Data Analysis"
author: "Enes K. Ergin (@eneskemalergin)"
last_reviewed: "2026-06-06"
tags: [beginner, getting-started, data-formats, dda, dia]
status: current
---

# Beginner's Guide to Proteomics Data Analysis

> **TL;DR:** Proteomics data starts as a vendor-specific raw file from a mass spectrometer. You convert it to an open format (usually mzML), run a search engine to identify peptides and proteins, quantify them, then apply statistics. If you remember only one thing: figure out what file format you have and what acquisition type (DDA, DIA, or targeted) produced it, because those two facts decide every tool choice that follows.

## The question

You have just been handed a folder of proteomics data, or you are about to generate some, and you are staring at file extensions you do not recognize. What are these files? What experiment produced them? How do you get from raw instrument output to a list of proteins you can interpret? This guide answers those questions in order, with data formats first, because the format barrier is the one that stops most newcomers.

## The workflow at a glance

Almost every bottom-up proteomics analysis follows the same path:

`Sample prep -> LC-MS/MS instrument -> Raw file -> (Convert to mzML if needed) -> Identify peptides -> Quantify -> Statistics -> Visualization and interpretation`

The rest of this guide walks through each stage and points to the tools in the [awesome list](../README.md) that handle it.

## Start with the file format

The most common beginner question is "how do I just open this file?" Proteomics uses several format families, and knowing which one you have tells you what to do next.

**Raw vendor formats** come straight off the instrument. They are proprietary and tied to the manufacturer:

- Thermo: `.raw` (a single file)
- Bruker: `.d` (a folder, not a file)
- SCIEX: `.wiff` and `.wiff2`
- Agilent: `.d` (a folder)
- Waters: `.raw` (a folder)

Here is the nuance most beginners miss: many modern tools read these vendor formats directly, so conversion is not always required. FragPipe and MaxQuant read Thermo `.raw`, DIA-NN and FragPipe read Bruker `.d` (FragPipe actually recommends keeping `.d` native), and Skyline and MetaMorpheus read several vendor formats natively. The catch is that direct vendor reading usually depends on Windows, because vendors like Thermo ship only Windows libraries. You convert to an open format when your tool needs it, when you work on Linux or macOS, when you want to archive in a standard format, or for special cases like demultiplexing overlapping DIA windows.

**Open exchange formats** are the standardized, vendor-neutral formats most analysis tools expect:

- `mzML` is the current HUPO-PSI community standard for raw spectra. When you do need an open format, this is the one to target.
- `mzXML` is an older format you still see in legacy pipelines.

**Identification result formats** store which peptides matched which spectra:

- `mzIdentML` (`.mzid`) is the HUPO-PSI standard for identification results.
- `pepXML` is the Trans-Proteomic Pipeline format you encounter across many tools.

**Quantification and reporting formats** store the final numbers:

- `mzTab` is the HUPO-PSI standard for reporting identifications and quantities in one readable table.
- Most tools also emit their own tables (for example MaxQuant text output, or the DIA-NN report) that you load directly into R, Python, or a stats tool.

When you do convert, the two standard tools are [ThermoRawFileParser](../README.md#data-repositories--standards) for Thermo data (cross-platform, so it works on Linux and macOS) and [ProteoWizard](../README.md#data-repositories--standards) (msconvert), which handles nearly every vendor but relies on Windows-only vendor libraries for most formats. Both are listed under Data Repositories & Standards.

## Know your acquisition type

The second fact that decides everything is how the mass spectrometer collected the data. There are three common modes:

- **DDA (data-dependent acquisition):** the instrument picks the most intense peptides in each scan and fragments them one at a time. This is the classic shotgun mode, supported by nearly every search engine.
- **DIA (data-independent acquisition):** the instrument fragments everything within defined mass windows, producing richer but more complex data. DIA needs dedicated software and has become the default for many quantitative studies.
- **Targeted (SRM/MRM and PRM):** you measure a predefined list of peptides with high sensitivity and reproducibility, typically for validation or clinical assays.

If you do not know which mode produced your data, ask whoever ran the instrument. The acquisition type narrows your tool choices immediately.

## Where proteomics data lives

Public proteomics data is centralized under [ProteomeXchange](../README.md#data-repositories--standards), which routes submissions to member repositories:

- **PRIDE** (at EMBL-EBI) is the largest general-purpose repository.
- **MassIVE** (at UC San Diego) hosts data and supports reanalysis.
- **jPOST** and **iProX** are the Japanese and Chinese members.

If you want practice data, download a dataset from PRIDE or MassIVE and run it through the workflow below.

## How analysis actually works

For a typical bottom-up experiment, the stages map to tool categories in the list:

1. **Convert if needed.** If your tool does not read your vendor format directly, convert to mzML first (ThermoRawFileParser or msconvert). Many tools let you skip this step.
2. **Identify** peptides and proteins with a search engine that matches spectra against a protein sequence database (your FASTA file). Results are filtered to a false discovery rate (FDR), usually 1 percent, using a target-decoy approach, so your final list is statistically controlled rather than a raw pile of guesses. See [Discovery Proteomics](../README.md#discovery-proteomics) and [Bioinformatics > Identification](../README.md#identification).
3. **Quantify** the identified proteins, either label-free or with labels such as TMT or SILAC. See [Quantitative Proteomics](../README.md#quantitative-proteomics).
4. **Apply statistics** to find proteins that change between conditions. See [Bioinformatics > Statistical Analysis](../README.md#statistical-analysis).
5. **Visualize and interpret** the results, from volcano plots to pathway enrichment.

You will also need a protein sequence database (usually a [UniProt](../README.md#sequence--function-knowledge-bases) reference proteome) as the search target, typically with common contaminants added and decoy sequences appended for FDR estimation. Most tools can generate the decoys for you.

## Recommended first tools

You do not need to learn every tool. For a first project, a small set covers most situations:

- **DDA, all-in-one and beginner friendly:** [FragPipe](../README.md#discovery-proteomics) gives you a graphical pipeline built on MSFragger that handles identification and quantification end to end.
- **DIA:** [DIA-NN](../README.md#dia-tools) is a widely used, well-documented choice that supports both library-free and spectral-library workflows.
- **Targeted, and a strong teaching tool:** [Skyline](../README.md#targeted--srm--prm) has an active tutorial library and an approachable interface.
- **Downstream statistics:** [MSstats](../README.md#statistical-analysis) (scriptable, R based) or [Perseus](../README.md#statistical-analysis) (graphical) take you from a quantification table to differential results.

Pick the one that matches your acquisition type, follow its official tutorial with a public dataset, and you will have a complete analysis behind you.

## Where to learn more

For structured learning, the [General Resources](../README.md#general-resources) section lists beginner tutorials, free courses (EMBL-EBI, May Institute), textbooks, and key reviews. The [R for Mass Spectrometry](../README.md#start-here-tutorials--practical-guides) book is a good path if you want to learn the data structures hands on.

## Caveats

This guide covers bottom-up (peptide-centric) proteomics, the most common starting point. Top-down (intact protein) analysis, and specialized areas like glycoproteomics or cross-linking, have their own tools and formats covered elsewhere in the list. The tool recommendations here favor accessibility for newcomers and are not a claim that they are the only good options. Revisit this guide if your formats or tools look different from what your collaborators use.

## Links

- [Data Repositories & Standards](../README.md#data-repositories--standards) - converters, repositories, and format specs
- [Discovery Proteomics](../README.md#discovery-proteomics) - DDA search and quantification suites
- [Quantitative Proteomics](../README.md#quantitative-proteomics) - DIA and targeted quantification
- [Bioinformatics & Computational Tools](../README.md#bioinformatics--computational-tools) - the full computational toolbox
- [General Resources](../README.md#general-resources) - tutorials, courses, and reviews
- [File Format Cheat Sheet](file-format-cheat-sheet.md) - deeper reference on formats and conversion (planned)

---

*This guide reflects the author's experience as of the last reviewed date. Spot an error or something out of date? Open a [Discussion or update PR](../CONTRIBUTING.md#writing-a-guide) - guides are meant to be refreshed. When experts genuinely disagree and cannot reconcile, we also welcome [competing guides](../GOVERNANCE.md#guide-disagreements).*
