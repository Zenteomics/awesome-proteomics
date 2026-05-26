# Guides

Opinionated deep-dives, decision trees, and practical references for proteomics practitioners. Guides answer a specific question with a clear recommendation. They distinguish factual claims from personal opinions.

> **New to proteomics data?** Start with the [Beginner's Guide to Proteomics Data Analysis](beginners-guide.md).

## What is a guide?

A guide answers a question like "I have 50 DIA runs from a timsTOF. Which tool should I use?" It gives a recommendation, explains the reasoning, and points to relevant entries in the [awesome list](../README.md).

We publish two formats:

- **Full guides** (1,000-1,500 words): comparison tables, decision trees, and practical recommendations on a broad topic.
- **Mini-guides** (300-500 words): focused comparisons or decision trees on a narrow topic. A good first contribution.

When contributors disagree, we welcome competing guides. Both stay in the directory with cross-references.

## Published guides

*None yet. The first guides will ship during Phase 2 (Seed Content).*

## Planned guides

| Guide | Type | Status | Description |
| --- | --- | --- | --- |
| [Beginner's Guide to Proteomics Data Analysis](beginners-guide.md) | Full | Planned | Zero-jargon intro: data formats, experiment types, first tools, where to learn more |
| [File Format Cheat Sheet](file-format-cheat-sheet.md) | Reference | Planned | mzML, pepXML, mzTab, vendor formats, and a conversion table |
| [Tool Compatibility Matrix](compatibility-matrix.md) | Reference | Planned | Which tools read which vendor formats? |
| [Starter Packs](starter-packs.md) | Mini-guide | Planned | "What 3 tools do I need?" for DDA, DIA, PTMs, single-cell |
| [DIA Tools Comparison](dia-tools-comparison.md) | Full | Planned | DIA-NN vs Spectronaut vs MaxDIA vs others |
| [Single-Cell Proteomics Best Practices](single-cell-best-practices.md) | Full | Planned | Sample prep to quantification |
| [AI/ML and Foundation Models in Proteomics](ai-ml-in-proteomics.md) | Full | Planned | pLMs, spectrum prediction, retention time models |
| [PTM Analysis Strategy](ptm-analysis-strategy.md) | Full | Planned | Choosing enrichment, search, and localization tools by PTM type |
| [Emerging Trends in Proteomics](emerging-trends-2026.md) | Full | Planned | Annual review, updated each January |

## Writing a guide

1. **Propose**: Open a [Guide Proposal issue](https://github.com/zenteomics/awesome-proteomics/issues/new?template=guide-proposal.yml) with your title, abstract, and outline.
2. **Write**: Use the [guide template](GUIDE_TEMPLATE.md). Keep it under 1,500 words. Cite facts. Mark opinions.
3. **Submit**: Open a PR. One reviewer checks for accuracy, clarity, and tone.
4. **Publish**: After merge, your guide appears here and gets cross-linked from the relevant README section.

See [CONTRIBUTING.md](../CONTRIBUTING.md) for full details on the guide authorship track.

## Guide template

Every guide uses YAML frontmatter for metadata. See [GUIDE_TEMPLATE.md](GUIDE_TEMPLATE.md) for the full template.

Frontmatter fields:

- **title**: Guide title
- **author**: Your name and GitHub handle
- **last_reviewed**: Date of last review (YYYY-MM-DD)
- **tags**: Topic tags for categorization
- **status**: `current`, `outdated`, or `superseded_by: [link]`

The `status` field enables programmatic handling. A future website can display banners automatically, and stale detection becomes a script rather than a manual check.
