---
title: "File Format Cheat Sheet"
author: "Enes K. Ergin (@eneskemalergin)"
last_reviewed: "2026-06-07"
tags: [reference, data-formats, conversion, file-formats]
status: current
---

# File Format Cheat Sheet

> **TL;DR:** Proteomics files fall into a handful of families: vendor raw formats off the instrument, open spectrum formats (mzML and relatives), identification results (mzIdentML, pepXML), quantification reports (mzTab and tool-specific tables), spectral libraries, and the FASTA database you search against. Work out which family a file belongs to and both conversion and tool choice become obvious. The conversion table near the bottom is the part most people bookmark.

## The question

You have a folder full of unfamiliar extensions - `.raw`, `.d`, `.wiff`, `.mzML`, `.mzid`, `.pepXML`, `.blib` - and you need to know what each one is, what reads or writes it, and how to convert between them. This is a reference, not a tutorial: scan to the family you care about, or jump straight to the conversion table.

For a gentler walkthrough of where these files come from in a typical analysis, read the [Beginner's Guide](beginners-guide.md) first.

## How to tell what you have

A quick triage before the tables:

- **A single large binary file** named `.raw` - almost certainly Thermo.
- **A folder** named `something.d` - Bruker or Agilent (the internal files differ).
- **A folder** named `something.raw` - Waters.
- **A `.wiff` plus a `.wiff.scan` (or `.wiff2`)** - SCIEX.
- **An XML-like file** named `.mzML` or `.mzXML` - already converted to an open format, ready for most tools.
- **Files named like `msms.txt`, `report.tsv`, `.mzid`, `.pepXML`** - these are results, produced after a search, not raw spectra.

## 1. Raw vendor (instrument) formats

Proprietary formats written directly by the mass spectrometer. Many modern tools read them natively, though often only on Windows because vendor libraries are Windows-only. Convert when your tool, operating system, or archive requires it.

| Format | Extension | Vendor | Notes |
| --- | --- | --- | --- |
| Thermo RAW | `.raw` (single file) | Thermo Fisher | The most common raw format in practice. Read natively by FragPipe, MaxQuant, and MetaMorpheus on Windows; converted cross-platform by ThermoRawFileParser. |
| Bruker | `.d` (folder) | Bruker | A folder holding `analysis.tdf` (timsTOF, with TIMS ion-mobility data), `analysis.tsf` (timsTOF fleX MALDI, no ion mobility), or `analysis.baf` (QTOF). The `.tdf`/`.tsf` files are SQLite-based. Read natively by DIA-NN and FragPipe. |
| SCIEX WIFF | `.wiff` + `.wiff.scan`, `.wiff2` | SCIEX | Always travels with its companion `.scan` file. Conversion needs vendor DLLs on Windows. |
| Agilent | `.d` (folder) | Agilent | Same extension as Bruker but a different internal layout (MassHunter `.bin`/`.xml` files). |
| Waters | `.raw` (folder) | Waters | A folder despite the name (MassLynx `_FUNC`/`.dat` files). Can also hold ion-mobility (IMS) data on Synapt instruments. |
| Shimadzu | `.lcd` | Shimadzu | Less common in proteomics; convertible via msconvert with vendor support. |
| Bruker legacy | `.yep`, `.fid` | Bruker | Older Bruker (and shared Agilent) ion-trap (`.yep`) and MALDI (`.fid`) containers you may meet in archived datasets. |

## 2. Open / standardized spectrum formats

Vendor-neutral formats that hold the actual spectra. These are what most analysis tools expect as input.

| Format | Extension | Steward | Notes |
| --- | --- | --- | --- |
| mzML | `.mzML` | HUPO-PSI | Current community standard (v1.1.0, 2009). The format to target when you convert. Supports profile and centroid data, plus ion mobility. |
| mzXML | `.mzXML` | ISB/SPC | Older standard, still seen in legacy TPP pipelines. Superseded by mzML. |
| mzData | `.mzData` | HUPO-PSI | Deprecated. Merged with mzXML to form mzML; you will only meet it in old datasets. |
| MGF (Mascot Generic Format) | `.mgf` | Matrix Science | Plain-text MS2 peak lists. Common search-engine input; drops most metadata. |
| MS1 / MS2 / BMS2 / CMS2 | `.ms1`, `.ms2` | - | Simple text or binary peak lists used by SEQUEST, Crux, and some DIA tooling. |
| DTA | `.dta` | Thermo / SEQUEST | Legacy single-spectrum text format. |
| PKL | `.pkl` | Waters / Micromass | Legacy peak-list format. |
| mz5 | `.mz5` | - | HDF5-based binary encoding of mzML for faster random access. |
| mzMLb | `.mzMLb` | - | HDF5-backed, standards-compliant version of mzML distributed via ProteoWizard; efficient for very large files. |

> **Imaging MS:** mass spectrometry imaging uses **imzML** (a `.imzML` metadata file plus an `.ibd` binary), the HUPO-PSI imaging standard. Different subfield, same family idea.

## 3. Identification result formats

Written after a search engine matches spectra to peptides. They store peptide-spectrum matches (PSMs), scores, and FDR.

| Format | Extension | Origin | Notes |
| --- | --- | --- | --- |
| mzIdentML | `.mzid` | HUPO-PSI | Standard for identification results; interchange between search engines and validators. |
| pepXML | `.pepXML`, `.pep.xml` | Trans-Proteomic Pipeline | Common PSM format across TPP, Comet, MSFragger, and others. |
| protXML | `.protXML`, `.prot.xml` | Trans-Proteomic Pipeline | Protein-level inference output (ProteinProphet). |
| Percolator in/out | `.pin` (in), `.pout` / `.tsv` (out) | Percolator | Tab-delimited feature table for rescoring PSMs. |
| idXML | `.idXML` | OpenMS | OpenMS-internal identification format. |
| Mascot result | `.dat` | Matrix Science | Mascot's native result file. |
| Search-engine tables | `.tsv`, `.txt` | various | FragPipe `psm.tsv`, MaxQuant `msms.txt`/`evidence.txt`, Sage `results.sage.tsv`. Human-readable PSM and peptide tables. |

## 4. Quantification & reporting formats

The final numbers - abundances per peptide or protein, ready for statistics.

| Format | Extension | Origin | Notes |
| --- | --- | --- | --- |
| mzTab | `.mzTab` | HUPO-PSI | Standard tab-delimited report combining identifications and quantities in one readable file. |
| MaxQuant output | `.txt` | MaxQuant | `proteinGroups.txt`, `peptides.txt`, `evidence.txt` in the `txt/` folder. Load directly into R, Python, or Perseus. |
| DIA-NN report | `.tsv`, `.parquet`, `.stats` | DIA-NN | Main report plus a Parquet variant for large cohorts. |
| Spectronaut report | `.tsv`, `.xls` | Biognosys | Configurable export schema. |
| Skyline document | `.sky`, `.skyd`, `.sky.zip`, `.skyp` | Skyline | `.sky` is the document, `.skyd` the cached chromatograms, `.sky.zip` a shareable bundle. |

## 5. Spectral library formats

Reference spectra used by DIA and library-based searches.

| Format | Extension | Tool / ecosystem | Notes |
| --- | --- | --- | --- |
| BiblioSpec | `.blib` | Skyline | SQLite-based library used throughout the Skyline ecosystem. |
| NIST MSP | `.msp` | NIST | Plain-text reference library, widely interchangeable. |
| SpectraST | `.sptxt` + `.splib` | TPP | Text and binary spectral library pair. |
| OpenSWATH assay | `.pqp`, `.tsv`, `.TraML` | OpenSWATH | Peptide-query-parameter library and transition lists. |
| EncyclopeDIA | `.dlib`, `.elib` | EncyclopeDIA | SQLite DIA libraries (`.dlib` predicted, `.elib` empirical). |
| DIA-NN library | `.speclib`, `.parquet` | DIA-NN | DIA-NN's compact spectral library; convertible to `.tsv`, with a newer `.parquet` form (DIA-NN 1.9.1+). |
| Spectronaut library | `.kit` | Biognosys | Biognosys library format; Spectronaut also imports plain-text `.tsv`/`.csv`/`.xls` libraries. |

## 6. Sequence database & transition formats

What you search against, and targeted-assay definitions.

| Format | Extension | Notes |
| --- | --- | --- |
| FASTA | `.fasta`, `.fa` | The protein sequence database, usually a UniProt reference proteome. Add contaminants and decoys before searching; most tools append decoys for you. See [UniProt](../README.md#sequence--function-knowledge-bases). |
| TraML | `.TraML` | HUPO-PSI standard for SRM/MRM/PRM transition lists. |
| Transition / assay lists | `.tsv`, `.csv` | Tool-specific targeted method and transition tables (Skyline, OpenSWATH). |

## The Rosetta Stone conversion table

The mapping that answers "I have X, how do I get to something my tool reads?" Watch the platform notes: most vendor libraries are Windows-only.

| You have | Convert with | You get | Then feed into |
| --- | --- | --- | --- |
| Thermo `.raw` | ThermoRawFileParser (cross-platform) or msconvert | mzML / MGF | FragPipe, DIA-NN, MaxQuant, MetaMorpheus |
| Bruker `.d` (timsTOF) | Read natively, or msconvert | mzML | DIA-NN, FragPipe |
| SCIEX `.wiff` / `.wiff2` | msconvert (vendor DLLs, Windows) | mzML | DIA-NN, OpenSWATH, Skyline |
| Agilent `.d` | msconvert (Windows) | mzML | most search engines |
| Waters `.raw` | msconvert (Windows) | mzML | most search engines |
| Overlapping / staggered DIA (any vendor) | msconvert with demultiplexing | demuxed mzML | DIA search tools |
| mzML / mzXML | search engine (MSFragger, Comet, Sage) | pepXML / mzIdentML | Percolator, TPP, Philosopher |
| pepXML | TPP (PeptideProphet, ProteinProphet) | protXML | protein inference and reporting |
| mzML | DIA-NN | report.tsv / .parquet | MSstats, R/Python stats |

Conversion tools live under [Data Repositories & Standards](../README.md#data-repositories--standards): [ThermoRawFileParser](../README.md#data-repositories--standards) is cross-platform for Thermo data, and [ProteoWizard](../README.md#data-repositories--standards) (msconvert) covers nearly every vendor but needs Windows for most vendor libraries. For Bruker timsTOF handling, see also AlphaTims under [Advanced MS Applications](../README.md#advanced-ms-applications).

## A note on completeness

**This is not a full or exhaustive list of proteomics file formats.** It covers the formats you are most likely to meet in mainstream bottom-up and DIA work. Many others exist: instrument-specific containers, deprecated formats, lab-internal conventions, metabolomics and imaging variants (mzTab-M, imzML), HDF5 derivatives, and formats specific to top-down, cross-linking, or ion-mobility workflows. New formats also appear as instruments and standards evolve. If you hit an extension that is not listed here, check the tool's documentation or the [HUPO-PSI standards](../README.md#data-repositories--standards) site, and consider opening a PR to extend this sheet.

## Caveats

Native vendor reading often depends on the operating system (Windows for most Thermo, SCIEX, Agilent, and Waters libraries), so the same tool may behave differently on Linux or macOS. Format support also changes between tool versions. When in doubt, mzML is the safest interchange target. This sheet reflects the common state of the field as of the last reviewed date.

## Links

- [Beginner's Guide to Proteomics Data Analysis](beginners-guide.md) - where these formats fit in the workflow
- [Data Repositories & Standards](../README.md#data-repositories--standards) - converters, repositories, and format specs
- [Discovery Proteomics](../README.md#discovery-proteomics) - DDA search and quantification suites
- [DIA Tools](../README.md#dia-tools) - DIA software that consumes these formats
- [Targeted / SRM / PRM](../README.md#targeted--srm--prm) - Skyline and targeted assay tools
- [Tool Compatibility Matrix](compatibility-matrix.md) - which tools read which formats

---

*This guide reflects the author's experience as of the last reviewed date. Spot an error or something out of date? Open a [Discussion or update PR](../CONTRIBUTING.md#writing-a-guide) - guides are meant to be refreshed. When experts genuinely disagree and cannot reconcile, we also welcome [competing guides](../GOVERNANCE.md#guide-disagreements).*
