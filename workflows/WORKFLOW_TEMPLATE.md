---
title: "Workflow Title"
author: "Your Name (@github_handle)"
last_reviewed: "YYYY-MM-DD"
tags: [dda, label-free, quantification]
status: current  # current | outdated | superseded_by: [link]
instrument_tested: "Thermo Exploris 480"  # optional: instrument used for testing
---

# Workflow Title

> **What this does:** One-sentence summary. Example: "Takes Thermo .raw files from a label-free DDA experiment and produces a quantified protein matrix with statistical testing."

## Prerequisites

- **Input**: What files does the user need? (e.g., Thermo .raw files, FASTA database)
- **Compute**: Minimum requirements (RAM, disk, GPU if applicable)
- **Software**: List all tools with versions and install links

## Pipeline overview

Raw files --> [Step 1: Convert] --> mzML --> [Step 2: Search] --> pepXML --> [Step 3: Quantify] --> protein matrix --> [Step 4: Stats] --> results

## Step 1: Raw data conversion

- **Tool**: [ThermoRawFileParser](../README.md#data-repositories--standards)
- **Input**: `.raw` files
- **Output**: `.mzML` files

**Alternatives**: [ProteoWizard msconvert](../README.md#data-repositories--standards) (GUI available, broader format support)

## Step 2: Database search

- **Tool**: [MSFragger via FragPipe](../README.md#discovery-proteomics)
- **Input**: `.mzML` files + `.fasta` database
- **Output**: pepXML, protein identification

**Alternatives**: [MaxQuant](../README.md#discovery-proteomics) (GUI-based, widely used), [Comet](../README.md#discovery-proteomics) (fast, CLI-first)

## Step 3: Quantification

*Continue the pattern for each step...*

## Step 4: Statistical analysis

*Continue the pattern...*

## Nextflow/Snakemake config

For automated, reproducible runs, include a config snippet here.

## Troubleshooting

Common issues and solutions:

- **Problem**: MSFragger runs out of memory on large datasets
    - **Fix**: Increase JVM heap size with `-Xmx64g`

## What I would change

Personal notes on what works and what you would do differently next time.

## Links

- All tools linked to their entries in the [awesome list](../README.md)
- [Relevant paper](https://doi.org/...)

---

*This workflow was tested on [instrument] with [n] samples. Your mileage may vary. If you find a better approach, please open a PR or start a [Discussion](https://github.com/zenteomics/awesome-proteomics/discussions).*

Example shell commands for reference (paste into relevant steps when writing a real workflow):

```bash
# Step 1: Convert .raw to .mzML
ThermoRawFileParser -d /path/to/raw/ -o /path/to/mzml/ -f 2

# Step 2: Run FragPipe
fragpipe --workflow LFQ --input-dir /path/to/mzml/ \
  --database /path/to/uniprot.fasta --output /path/to/results/
```

Example Nextflow config:

```groovy
process {
    container = 'ghcr.io/zenteomics/awesome-proteomics-dda:latest'
    cpus = 8
    memory = '32 GB'
}
```
