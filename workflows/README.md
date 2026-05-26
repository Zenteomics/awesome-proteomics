# Workflows

Start-to-finish pipelines for common proteomics experiments. Each workflow walks you through raw data to results, with specific tool chains, code snippets, and notes on alternatives.

Each workflow picks specific tools and explains why. If you disagree with a choice, check the alternatives section or propose a competing workflow.

## What is a workflow?

A workflow answers: "I have this type of experiment. What do I actually run?"

Every workflow includes:

- A clear task description and expected input/output
- Step-by-step tool chain with links back to the [awesome list](../README.md)
- Code snippets (shell commands, Nextflow, or Snakemake configs)
- Notes on alternatives at each step
- Interoperability notes: what format goes in, what comes out

## Published workflows

*None yet. The first workflow will ship during Phase 2 (Seed Content).*

## Planned workflows

| Workflow | Status | Description |
| --- | --- | --- |
| [Label-Free DDA Quantification](label-free-dda.md) | Planned | Raw files to volcano plots. ThermoRawFileParser, MSFragger/FragPipe, IonQuant, MSstats. |
| [DIA Analysis](dia-analysis.md) | Planned | Library-based and library-free approaches. DIA-NN and Spectronaut paths. |
| [Phosphoproteomics](phosphoproteomics.md) | Planned | Enrichment to localization scoring. IMAC/TiO2 to MaxQuant/MSFragger. |
| [Single-Cell Proteomics](single-cell.md) | Planned | Sample prep to quantification. SCoPE2, plexDIA, and label-free approaches. |

## Writing a workflow

1. **Propose**: Open a [Guide Proposal issue](https://github.com/zenteomics/awesome-proteomics/issues/new?template=guide-proposal.yml) (select "Workflow" as the type).
2. **Write**: Use the [workflow template](WORKFLOW_TEMPLATE.md). Include real commands and config snippets.
3. **Submit**: Open a PR. One reviewer checks for accuracy and reproducibility.
4. **Publish**: After merge, your workflow appears here and gets cross-linked from the relevant README section.

See [CONTRIBUTING.md](../CONTRIBUTING.md) for full details.

## Workflow template

Every workflow uses YAML frontmatter. See [WORKFLOW_TEMPLATE.md](WORKFLOW_TEMPLATE.md) for the full template
