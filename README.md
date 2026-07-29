<!-- markdownlint-disable MD007 MD010 MD033 MD036 MD041 -->

<p align="center">
  <img src="media/awesome_proteomics-icon.png" alt="Awesome Proteomics" width="240">
</p>

<h1 align="center">Awesome Proteomics</h1>

<p align="center">
  A curated list of tools, resources, and knowledge for mass spectrometry-based proteomics - covering both bottom-up (peptide-centric) and top-down (proteoform-centric) approaches.
</p>

<p align="center">
  <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-CC0_1.0-9B59B6?style=flat-square" alt="CC0 1.0"></a>
  <!-- <a href="https://github.com/zenteomics/awesome-proteomics/actions/workflows/ci.yml"><img src="https://img.shields.io/github/actions/workflow/status/zenteomics/awesome-proteomics/ci.yml?branch=main&style=flat-square&logo=github&label=CI" alt="CI"></a>
  <a href="https://doi.org/10.5281/zenodo.XXXXXXX"><img src="https://img.shields.io/badge/doi-10.5281%2Fzenodo.XXXXXXX-2C8EBB?style=flat-square" alt="DOI"></a> -->
  <a href="CONTRIBUTING.md"><img src="https://img.shields.io/badge/contributions-welcome-27AE60?style=flat-square" alt="Contributions Welcome"></a>
</p>

<p align="center">
  <a href="guides/"><img src="https://img.shields.io/badge/guides-deep--dives-8E44AD?style=flat-square" alt="Guides"></a>
  <a href="workflows/"><img src="https://img.shields.io/badge/workflows-pipelines-2980B9?style=flat-square" alt="Workflows"></a>
  <a href="GOVERNANCE.md"><img src="https://img.shields.io/badge/governance-how_we_run-16A085?style=flat-square" alt="Governance"></a>
  <a href="CODE_OF_CONDUCT.md"><img src="https://img.shields.io/badge/code_of_conduct-Contributor_Covenant-E74C3C?style=flat-square" alt="Code of Conduct"></a>
</p>

> **New to proteomics data?** [Start here &rarr;](guides/beginners-guide.md)

**Project Health** &middot; Links Verified: 2026-06-29 | New Tools this Month: &mdash; | Stale Entries Pruned: &mdash;

_Inclusion does not constitute endorsement. Commercial tools are marked with 💰. See the [contribution guidelines](CONTRIBUTING.md) for entry format and quality bar._

**Scope:** Mass spectrometry-based proteomics. The list currently leans toward bottom-up / shotgun proteomics, with top-down / native approaches covered more selectively while our coverage grows. Affinity- and aptamer-based platforms (for example Olink and SomaScan) are out of scope; this list deliberately stays MS-focused.

---

## Contents

- [Contents](#contents)
- [Legend](#legend)
- [General Resources](#general-resources)
  - [Start Here: Tutorials \& Practical Guides](#start-here-tutorials--practical-guides)
  - [Courses \& Training](#courses--training)
  - [Books](#books)
  - [Reference \& Standards](#reference--standards)
  - [Reviews \& Perspectives](#reviews--perspectives)
  - [Milestone Papers](#milestone-papers)
  - [Blogs, Podcasts \& Media](#blogs-podcasts--media)
- [Mass Spectrometry Fundamentals](#mass-spectrometry-fundamentals)
  - [Advanced MS Applications](#advanced-ms-applications)
- [Sample Preparation](#sample-preparation)
- [Discovery Proteomics](#discovery-proteomics)
- [Top-Down Proteomics](#top-down-proteomics)
- [Quantitative Proteomics](#quantitative-proteomics)
  - [DIA Tools](#dia-tools)
  - [Targeted / SRM / PRM](#targeted--srm--prm)
  - [Label-Based Quantification (TMT, SILAC, iTRAQ)](#label-based-quantification-tmt-silac-itraq)
- [Post-Translational Modifications](#post-translational-modifications)
  - [Phosphoproteomics](#phosphoproteomics)
  - [Glycoproteomics](#glycoproteomics)
  - [Ubiquitination \& Other PTMs](#ubiquitination--other-ptms)
- [Single-Cell Proteomics](#single-cell-proteomics)
- [Bioinformatics \& Computational Tools](#bioinformatics--computational-tools)
  - [Identification](#identification)
  - [Quantification](#quantification)
  - [Statistical Analysis](#statistical-analysis)
  - [Visualization](#visualization)
  - [Quality Control](#quality-control)
  - [Pipelines \& Frameworks](#pipelines--frameworks)
  - [Cloud \& HPC](#cloud--hpc)
- [AI \& Machine Learning in Proteomics](#ai--machine-learning-in-proteomics)
  - [Foundation Models / Protein Language Models (pLMs)](#foundation-models--protein-language-models-plms)
- [Data Repositories \& Standards](#data-repositories--standards)
- [Protein Databases \& Knowledge Bases](#protein-databases--knowledge-bases)
  - [Sequence \& Function Knowledge Bases](#sequence--function-knowledge-bases)
  - [Structure Databases](#structure-databases)
  - [Families, Domains \& Ontologies](#families-domains--ontologies)
  - [Enzymes \& Peptidases](#enzymes--peptidases)
  - [Pathways \& Interactions](#pathways--interactions)
  - [Disease, Drug \& Target Knowledge Bases](#disease-drug--target-knowledge-bases)
  - [Expression \& Proteoform Atlases](#expression--proteoform-atlases)
- [Multi-Omics Integration](#multi-omics-integration)
- [Frontier \& Niche Techniques](#frontier--niche-techniques)
  - [Metaproteomics](#metaproteomics)
  - [Proteogenomics](#proteogenomics)
  - [Other Emerging Approaches](#other-emerging-approaches)
- [Deprecated \& Legacy](#deprecated--legacy)
- [Community \& Organizations](#community--organizations)
- [Guides \& Workflows](#guides--workflows)
- [Contributing](#contributing)
- [License](#license)

---

## Legend

Each entry follows the format `[Name](link) - One-line description.` with optional tags so you can tell, at a glance, how to run a tool and what it does.

**Interface** - how you use it:

| Tag     | Meaning                                                                   |
| ------- | ------------------------------------------------------------------------- |
| `[CLI]` | Runs from the command line (terminal tool or script)                      |
| `[GUI]` | Graphical desktop or web application                                      |
| `[API]` | Importable library or package you call from code (Python, R, and similar) |

**Data type / workflow** - what it processes:

| Tag            | Meaning                                       |
| -------------- | --------------------------------------------- |
| `[DDA]`        | Data-dependent acquisition                    |
| `[DIA]`        | Data-independent acquisition (includes SWATH) |
| `[Label-Free]` | Label-free quantification                     |
| `[TMT]`        | Isobaric labeling (TMT / iTRAQ)               |
| `[SILAC]`      | Metabolic labeling (SILAC)                    |
| `[Targeted]`   | Targeted assays (SRM / PRM)                   |

**Status** - maturity and licensing:

| Emoji | Meaning                                                     |
| ----- | ----------------------------------------------------------- |
| 💰    | Commercial or paid license (a free academic tier may exist) |
| 📦    | Containerized image available (Docker / Singularity)        |
| 🏭    | Production-grade / built for high throughput                |
| 🧪    | Experimental / research-stage                               |

**Platform** - shown only when support is non-obvious or restricted:

| Emoji | Meaning |
| ----- | ------- |
| 🐧    | Linux   |
| 🪟    | Windows |
| 🍎    | macOS   |

Tags stack: a single entry can read `[DIA]` `[CLI]` 🐧 🪟. No platform emoji means the tool is broadly cross-platform or runs in the browser.

---

## General Resources

_Last Verified: Q2 2026_

> Start-here guides, courses, books, key reviews, milestone papers, and community media. Includes clinical and medical proteomics resources until that subfield warrants its own section.

### Start Here: Tutorials & Practical Guides

- [A beginner's guide to mass spectrometry-based proteomics](https://portlandpress.com/biochemist/article/42/5/64/226371/A-beginner-s-guide-to-mass-spectrometry-based) - Open-access introduction by Sinha and Mann (2020, The Biochemist) to mass spectrometer components, sample preparation, and quantification strategies.
- [An Introduction to Mass Spectrometry-Based Proteomics](https://doi.org/10.1021/acs.jproteome.2c00838) - Illustrated tutorial by Shuken (2023, Journal of Proteome Research) covering a label-free quantitative experiment from sample preparation to protein-group analysis.
- [Comprehensive Overview of Bottom-Up Proteomics Using Mass Spectrometry](https://doi.org/10.1021/acsmeasuresciau.3c00068) - Crowd-sourced handbook by Jiang, Meyer, et al. (2024, ACS Measurement Science Au) covering the bottom-up workflow from biochemistry basics to biological interpretation, maintained as a living tutorial at [proteomics-tutorial](https://jessegmeyerlab.github.io/proteomics-tutorial/). (open access)
- [A researcher's guide to mass spectrometry-based proteomics](https://doi.org/10.1002/pmic.201600113) - Overview (2016, Proteomics) of experimental design and workflow choices for newcomers to MS-based proteomics.
- [Data-independent acquisition-based SWATH-MS for quantitative proteomics: a tutorial](https://doi.org/10.15252/msb.20178126) - Tutorial by Ludwig et al. (2018, Molecular Systems Biology) on designing and analyzing DIA/SWATH-MS experiments. (open access)
- [R for Mass Spectrometry](https://rformassspectrometry.github.io/book/) - Online book teaching mass spectrometry and proteomics data handling and analysis with the R for Mass Spectrometry packages.
- [Expasy](https://www.expasy.org/) - SIB Swiss Bioinformatics Resource Portal cataloging 160+ databases and tools for protein analysis, proteomics, and related bioinformatics.
- [ProteomicsEducation (Payne Lab)](https://github.com/PayneLab/ProteomicsEducation) - Open Colab tutorials on computational proteomics (ID/quant) and peptide embeddings for machine learning ([paper](https://doi.org/10.1021/acs.jproteome.5c00563)).

### Courses & Training

- [EMBL-EBI Proteomics Bioinformatics](https://www.ebi.ac.uk/training/events/proteomics-bioinformatics) - Course covering search engines, quantification, data repositories, and downstream analysis.
- [Proteomics: An Introduction (EMBL-EBI)](https://www.ebi.ac.uk/training/online/courses/proteomics-an-introduction) - Free self-paced course introducing proteomics concepts and EMBL-EBI resources.
- [May Institute](https://computationalproteomics.khoury.northeastern.edu/) - Annual Northeastern University program on computation and statistics for MS-based proteomics with hands-on open-source tool training.
- [Broad Institute Proteomics Tutorials and Workshops](https://www.broadinstitute.org/proteomics/tutorials-and-workshops) - Tutorials and workshop materials on proteomics technologies and methods from the Broad Proteomics Platform.
- [Proteomics Academy](https://www.proteomics-academy.org/) - Free educational materials and a community Q&A forum maintained by EuBIC-MS and the EuPA education committee.
- [CompOmics Lectures](https://www.youtube.com/playlist?list=PLXxp6nsBenSX_W8DiOocKJ0laNauYNdYl) - Video lecture series from the CompOmics group covering mass spectrometry and computational proteomics fundamentals.

### Books

- [Introduction to Proteomics: Tools for the New Biology](https://link.springer.com/book/10.1007/978-1-59259-130-5) - Liebler (2002) textbook on protein and peptide separation, mass spectrometry, and data analysis for biologists; a lending copy is available at the [Internet Archive](https://archive.org/details/introductiontopr0000lieb).
- [Computational and Statistical Methods for Protein Quantification by Mass Spectrometry](https://onlinelibrary.wiley.com/doi/book/10.1002/9781118494042) - Eidhammer, Barsnes, Eide, and Martens (2013, Wiley) textbook on the computational and statistical foundations of protein identification and quantification.

### Reference & Standards

> Reporting guidelines, terminology, and community reference studies. For data formats and controlled vocabularies see [Data Repositories & Standards](#data-repositories--standards).

- [HUPO-PSI Minimum Reporting Guidelines (MIAPE)](https://www.psidev.info/miape) - Community-developed guidelines specifying the minimum information needed to report and interpret a proteomics experiment.
- [Definitions of Terms Relating to Mass Spectrometry (IUPAC Recommendations)](https://doi.org/10.1351/PAC-REC-06-04-06) - Murray et al. (2013, Pure and Applied Chemistry) reference defining standardized mass spectrometry terminology.
- [ABRF Proteomics Research Groups (sPRG / iPRG)](https://abrf.org/research-groups/proteomics-research-group-prg/) - Community research groups that run collaborative studies producing reference standards, benchmark datasets, and method comparisons.
- [ProteoBench](https://proteobench.readthedocs.io/en/stable/) - Community-curated platform for comparing proteomics data analysis workflows (DDA/DIA LFQ, de novo, SCP modules) with public and private benchmark runs ([preprint](https://doi.org/10.64898/2025.12.09.692895)). `[CLI]` 🧪

### Reviews & Perspectives

- [Mass spectrometry-based proteomics](https://doi.org/10.1038/nature01511) - Aebersold and Mann (2003, Nature) review of the principles, instrumentation, and applications of MS-based proteomics.
- [The ABC's (and XYZ's) of peptide sequencing](https://doi.org/10.1038/nrm1468) - Steen and Mann (2004, Nature Reviews Molecular Cell Biology) primer on peptide fragmentation and tandem mass spectrometry.
- [Quantitative, high-resolution proteomics for data-driven systems biology](https://doi.org/10.1146/annurev-biochem-061308-093216) - Cox and Mann (2011, Annual Review of Biochemistry) review of high-accuracy quantitative proteomics methods.
- [Protein analysis by shotgun/bottom-up proteomics](https://doi.org/10.1021/cr3003533) - Zhang, Fonslow, Shan, Baek, and Yates (2013, Chemical Reviews) reference on the bottom-up proteomics workflow.
- [Mass-spectrometric exploration of proteome structure and function](https://doi.org/10.1038/nature19949) - Aebersold and Mann (2016, Nature) review of the scope and capabilities of MS-based proteomics.
- [Progress in top-down proteomics and the analysis of proteoforms](https://pubmed.ncbi.nlm.nih.gov/27306313/) - Toby, Fornelli, and Kelleher (2016, Annual Review of Analytical Chemistry) review of intact-protein top-down analysis.
- [Proteomic and interactomic insights into the molecular basis of cell functional diversity](https://doi.org/10.1038/s41580-020-0231-2) - Bludau and Aebersold (2020, Nature Reviews Molecular Cell Biology) review of how proteoforms, interactions, and modifications generate functional diversity.
- [Mass-spectrometry-based proteomics: from single cells to clinical applications](https://doi.org/10.1038/s41586-025-08584-0) - 2025 Nature review of advances in sample preparation, instrumentation, data acquisition, and single-cell and clinical applications.

### Milestone Papers

- [Proteoform: a single term describing protein complexity](https://doi.org/10.1038/nmeth.2369) - Smith, Kelleher, et al. (2013, Nature Methods) defines "proteoform" as the term for the molecular forms of a protein.
- [A draft map of the human proteome](https://doi.org/10.1038/nature13302) - Kim et al. (2014, Nature) mass spectrometry profiling of 30 human tissues and cell types covering proteins from about 84% of protein-coding genes.
- [Mass-spectrometry-based draft of the human proteome](https://pubmed.ncbi.nlm.nih.gov/24870543/) - Wilhelm et al. (2014, Nature) draft human proteome assembled from large-scale datasets and released through the ProteomicsDB database.
- [The Human Proteoform Project: defining the human proteome](https://doi.org/10.1126/sciadv.abk0734) - Smith, Kelleher, et al. (2021, Science Advances) proposal for a reference set of human proteoforms.

### Blogs, Podcasts & Media

- [News in Proteomics Research](https://proteomicsnews.blogspot.com/) - Community blog by Ben Orsburn covering new papers, tools, and methods.
- [The Proteomics Show](https://open.spotify.com/show/3R8aGNVMKwfovkWWRVnu4E) - Interview podcast hosted by Ben Orsburn and Ben Neely featuring proteomics researchers.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Mass Spectrometry Fundamentals

_Last Verified: Q2 2026_

> Instrument principles, ionization methods, mass analyzers, and data formats. Includes advanced MS applications (spatial proteomics, structural MS, HDX-MS, XL-MS, ion mobility, native MS) as sub-topics.
>
> Conceptual introductions to instrumentation and workflows are listed under [General Resources](#general-resources). The tools below help interpret spectra and plan experiments.

- [Protein Prospector](https://prospector.ucsf.edu/) - Web suite for MS-based sequence database searching with utilities (MS-Product, MS-Digest, MS-Isotope) for calculating fragment ions, in silico digests, and isotope patterns.
- [ChemCalc](https://www.chemcalc.org/) - Web toolset for calculating molecular masses, isotopic distributions, and peptide and protein fragmentation.
- [UW Proteomics Resource Tools](https://proteomicsresource.washington.edu/protocols06/) - Collection of online calculators for MS/MS fragmentation, in silico digestion, isotope distributions, and peptide masses.

### Advanced MS Applications

> Structural and specialized MS techniques: cross-linking (XL-MS), hydrogen-deuterium exchange (HDX-MS), thermal proteome profiling and CETSA, limited proteolysis (LiP-MS), ion mobility, and spatial proteomics.

- [pLink](https://github.com/pFindStudio/pLink2) - Search engine for identifying cross-linked peptides (XL-MS) with built-in false discovery rate control. `[GUI]` 🪟
- [XL-MSDigger](https://github.com/Chen-micslab/XL-MSDigger) - Deep learning XL-MS platform (Deep4D-XL RT/CCS/MS2 prediction) for DDA rescoring (pLink/Scout) and DIA predicted-library analysis ([paper](https://doi.org/10.1038/s41467-026-69489-8)). `[CLI]` `[DIA]` `[DDA]`
- [XL-Ranker](https://github.com/bzhanglab/xlranker) - Parsimony plus XGBoost workflow that resolves ambiguous cross-linked peptide mappings into prioritized PPIs ([preprint](https://doi.org/10.1101/2025.07.18.665625)). `[CLI]` `[API]` 🧪
- [xiSEARCH](https://www.rappsilberlab.org/software/xisearch/) - Search engine for cross-linked peptides supporting cleavable and non-cleavable cross-linkers, paired with the xiVIEW visualization tool. `[GUI]`
- [xlms (decoy-free FDR)](https://github.com/shawn-peng/xlms) - Decoy-free FDR estimation for XL-MS/MS via skew-normal mixture modeling of ranked cross-link PSM scores ([paper](https://doi.org/10.1093/bioinformatics/btae233)). `[CLI]`
- [MeroX](https://www.stavrox.com/) - Software for identifying cross-linked peptides from MS-cleavable and non-cleavable cross-linkers. `[GUI]`
- [Kojak](https://www.kojak-ms.org/) - Open-source algorithm for identifying cross-linked peptides from tandem mass spectra. `[CLI]`
- [Deuteros 2.0](https://github.com/andymlau/Deuteros_2.0) - Open-source tool for processing, statistical analysis, and visualization of differential HDX-MS data. `[GUI]`
- [PyHDX](https://github.com/Jhsmit/PyHDX) - Python tool that derives residue-level protection factors and free energies from HDX-MS data. `[CLI]` `[API]`
- [TPP (Thermal Proteome Profiling)](https://bioconductor.org/packages/TPP) - R/Bioconductor package for analyzing thermal proteome profiling experiments across temperature or concentration ranges, including the NPARC model. `[CLI]`
- [mineCETSA](https://github.com/nkdailingyun/mineCETSA) - R package for processing and visualizing proteome-wide MS-CETSA target-engagement data. `[CLI]`
- [MSstatsLiP](https://bioconductor.org/packages/MSstatsLiP) - R/Bioconductor package for statistical analysis of limited proteolysis (LiP-MS) experiments at peptide and protein level. `[CLI]`
- [FLiPPR](https://github.com/FriedLabJHU/FragPipe-Limited-Proteolysis-Processor) - FragPipe post-processor for LiP-MS with LiP-aware imputation, data merging, and protein-centric multiple-hypothesis correction (flippr 0.3.0) ([paper](https://doi.org/10.1021/acs.jproteome.3c00887)). `[CLI]` `[API]`
- [PeptideVisualizer](https://github.com/kolocode/Peptide-Visualizer) - Open-source PROTOMAP analysis tool that builds MaxQuant peptographs with UniProt features and a mismatch factor to flag proteolytic events ([paper](https://doi.org/10.1021/acs.jproteome.5c01209)). `[GUI]` `[CLI]`
- [ProteoAutoNet](https://github.com/guomics-lab/ProteoAutoNet) - Robotics-assisted co-fractionation MS (CF-MS) workflow with XGBoost co-elution PPI prediction and data augmentation ([paper](https://doi.org/10.1038/s41467-026-68686-9)). `[CLI]` `[DIA]`
- [AlphaTims](https://github.com/MannLabs/alphatims) - Python package for fast access and visualization of Bruker timsTOF ion-mobility (TIMS-TOF) raw data. `[CLI]` `[API]`
- [pRoloc](https://bioconductor.org/packages/pRoloc) - R/Bioconductor framework using machine learning to assign proteins to subcellular compartments in spatial proteomics experiments, with the pRolocGUI visualization app. `[CLI]`
- [PEELing](https://github.com/JaneliaSciComp/peeling/) - Python package and web service for spatially resolved / proximity-labeling proteomics QC, contaminant cutoff, annotation, and visualization ([paper](https://doi.org/10.1093/bioinformatics/btaf439)). `[CLI]` `[GUI]` `[API]`
- [OpenDVP](https://github.com/CosciaLab/openDVP) - Open-source deep visual proteomics framework linking imaging (QuPath/Napari/MCMICRO) with SpatialData/AnnData and label-free proteomics ([preprint](https://doi.org/10.1101/2025.07.13.662099)). `[CLI]` `[API]` 🧪
- [AnnoSpat](https://github.com/faryabiLab/AnnoSpat) - Neural-network cell-type annotation and point-process spatial patterning for imaging mass cytometry (IMC) and CODEX spatial proteomics ([paper](https://doi.org/10.1038/s41467-024-47334-0)). `[CLI]` `[API]`
- [Corona](https://github.com/SchweppeLab/Corona) - Virtual mass spectrometer that replays scans in real time over Thermo IAPI / Helios so developers can build and test real-time MS instrument apps without hardware. `[GUI]` 🪟

> Native and intact-protein MS deconvolution is covered by UniDec under [Top-Down Proteomics](#top-down-proteomics); diaPASEF ion-mobility DIA is supported within [FragPipe](#discovery-proteomics) and [DIA-NN](#dia-tools).

**[&uarr; Back to Contents](#contents)**

## Sample Preparation

_Last Verified: Q2 2026_

> Protocols, method papers, kits, and bench-level resources. Includes [protocols.io](https://protocols.io) entries.

- [protocols.io](https://www.protocols.io/) - Repository for creating, sharing, and following step-by-step research protocols, including many proteomics sample-preparation methods.
- [SP3 (Single-Pot Solid-Phase-enhanced Sample Preparation)](https://doi.org/10.1038/s41596-018-0082-x) - Paramagnetic-bead protocol for protein cleanup and digestion across a wide range of input amounts (Hughes et al., 2019, Nature Protocols).
- [FASP (Filter-Aided Sample Preparation)](https://doi.org/10.1038/nmeth.1322) - Method that exchanges detergents for urea on an ultrafiltration device before on-filter digestion (Wisniewski et al., 2009, Nature Methods).
- [S-Trap](https://protifi.com/) - Suspension-trapping spin columns that capture SDS-solubilized proteins for rapid detergent removal and digestion. 💰
- [PreOmics iST](https://www.preomics.com/products/ist) - Cartridge-based kit performing lysis, digestion, and peptide cleanup in a single workflow for bottom-up proteomics. 💰
- [PeptideCutter](https://web.expasy.org/peptide_cutter/) - ExPASy web tool that predicts protease and chemical cleavage sites in a protein sequence.
- [Protein Digestion Simulator](https://github.com/PNNL-Comp-Mass-Spec/Protein-Digestion-Simulator) - In silico digestion tool that generates peptide lists and evaluates peptide uniqueness from protein sequences. `[GUI]` 🪟
- [ProteaseGuru](https://github.com/smith-chem-wisc/ProteaseGuru) - In silico digestion tool that compares multiple proteases across protein databases and visualizes peptide-level sequence coverage and uniqueness. `[GUI]` 🪟
- [Rapid Peptides Generator (RPG)](https://gitlab.pasteur.fr/nmaillet/rpg) - Command-line tool that predicts protease cleavage sites with support for multiple enzymes and custom rules. `[CLI]`
- [DigestedProteinDB](https://github.com/jankod/DigestedProteinDB) - Mass-indexed in silico peptide digest database (Java/RocksDB) with web and REST search by mass, sequence, or taxonomy ([portal](https://digestedproteindb.pbf.hr/)). `[CLI]` `[API]`

> Tissue and cell lysis, enrichment, and labeling steps are also handled within the suites under [Discovery Proteomics](#discovery-proteomics); PTM enrichment resources are listed under [Post-Translational Modifications](#post-translational-modifications).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Discovery Proteomics

_Last Verified: Q2 2026_

> Shotgun and bottom-up proteomics tools and resources. For intact-protein analysis see [Top-Down Proteomics](#top-down-proteomics); for computational analysis tools see also [Bioinformatics & Computational Tools](#bioinformatics--computational-tools).

&#x1F4D6; _Workflow:_ [Label-Free DDA](workflows/label-free-dda.md)

- [MaxQuant](https://maxquant.org/) - Suite for label-free, SILAC, and isobaric quantification from shotgun data, built on the Andromeda search engine. `[DDA]` `[Label-Free]` `[TMT]` `[SILAC]` `[GUI]` 🪟
- [FragPipe](https://fragpipe.nesvilab.org/) - Graphical pipeline built on MSFragger for DDA, DIA, and labeling workflows. `[DDA]` `[DIA]` `[TMT]` `[GUI]`
- [PeptideShaker](https://github.com/compomics/peptide-shaker) - Search-engine-independent platform for interpreting and visualizing identification results from multiple engines. `[DDA]` `[GUI]`
- [SearchGUI](https://github.com/compomics/searchgui) - Graphical interface to configure and run several open-source search engines together. `[DDA]` `[GUI]`
- [AlphaPept](https://github.com/MannLabs/alphapept) - Modular Python framework for DDA analysis, accelerated with Numba, with a GUI, command line, and scriptable API. `[DDA]` `[Label-Free]` `[GUI]` `[CLI]` `[API]`
- [Proteome Discoverer](https://www.thermofisher.com/us/en/home/industrial/mass-spectrometry/liquid-chromatography-mass-spectrometry-lc-ms/lc-ms-software/multi-omics-data-analysis/proteome-discoverer-software.html) - Commercial, extensible platform for identification, quantification, and PTM analysis across DDA and DIA. `[DDA]` `[DIA]` `[TMT]` `[GUI]` 💰 🪟
- [i2MassChroQ](http://pappso.inrae.fr/en/bioinfo/i2masschroq/) - Open-source DDA desktop suite (X!Tandem identification, protein inference, MassChroQ XIC quantification, MSstats) with native Bruker timsTOF PASEF support (v1.3.7; [paper](https://doi.org/10.1021/acs.jproteome.3c00732)). `[DDA]` `[Label-Free]` `[GUI]` `[CLI]`
- [PEAKS Studio](https://www.bioinfor.com/peaks-studio/) - Commercial suite combining de novo sequencing with database search for identification and quantification. `[DDA]` `[DIA]` `[GUI]` 💰 🪟
- [pFind](https://github.com/pFindStudio/pFind3) - Open-search engine (Open-pFind) for peptide identification, including unanticipated and unexpected modifications. `[DDA]` `[GUI]` 🪟
- [PatternLab for Proteomics](https://patternlabforproteomics.org/) - Integrated Windows GUI for shotgun proteomics (search through differential analysis); PatternLab V is the stable release and 5.1 adds Spectral Cruncher/SpecFormer ([protocols](https://doi.org/10.1038/s41596-022-00690-x)). `[DDA]` `[GUI]` 🪟
- [SequenceAssembler](https://patternlabforproteomics.org/sa/) - Windows ClickOnce tool that assembles full-length protein sequences from PSM and de novo results (PatternLab, Novor Cloud, PEAKS) ([paper](https://doi.org/10.1016/j.jprot.2025.105542)). `[GUI]` 🪟

> Search engines that power discovery (MSFragger, Comet, Sage) are listed under [Bioinformatics > Identification](#identification).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Top-Down Proteomics

_Last Verified: Q2 2026_

> Analysis of intact proteins and proteoforms without digestion, preserving PTMs, isoforms, and sequence variants. Complements the peptide-centric workflows under [Discovery Proteomics](#discovery-proteomics), and covers both denatured and native (complex-down) approaches.

- [TopPIC Suite](https://www.toppic.org/) - Open-source suite (TopFD, TopPIC, TopMG, TopDiff, TopDIA) for proteoform identification, characterization, and quantification from top-down data. `[DDA]` `[DIA]` `[CLI]` `[GUI]`
- [TopLib](https://github.com/toppic-suite/toplib) - Builds and searches top-down mass spectral libraries (TopFD/TopPIC → SQLite) for faster, more reproducible proteoform identification ([paper](https://doi.org/10.1021/acs.analchem.4c06627)). `[CLI]`
- [TopMGQuant](https://github.com/Zeirdo/TopMGQuant) - Alignment-graph method to identify and relatively quantify multiple proteoforms from a single top-down MS/MS spectrum ([paper](https://doi.org/10.1093/bioinformatics/btaf007)). `[CLI]`
- [TopRepo](https://github.com/toppic-suite/toprepo) - Top-down spectral repository (>18M MS/MS spectra from 12 species; curated library >5M annotated) for pan-dataset analysis, library search, and DL spectral prediction ([preprint](https://doi.org/10.64898/2026.02.20.707032)). 🧪
- [Informed-Proteomics (MSPathFinder)](https://github.com/PNNL-Comp-Mass-Spec/Informed-Proteomics) - Open-source package with ProMex feature finding and the MSPathFinder database search engine for top-down LC-MS/MS. `[CLI]` 🪟
- [MASH Explorer](https://labs.wisc.edu/gelab/MASH_Explorer/index.php) - Free environment integrating multiple deconvolution and search algorithms for denatured and native top-down proteomics. `[GUI]` 🪟
- [ProSightPD](https://www.proteinaceous.net/prosightpd) - Commercial high-throughput top-down search platform running as nodes within Thermo Proteome Discoverer. `[GUI]` 💰 🪟
- [ProSight Lite / PSLite Online](https://pslite.proteinaceous.net/) - Free vendor-agnostic fragment matching for a single candidate proteoform and its modifications; modern web app plus Windows desktop ([paper](https://doi.org/10.1002/jms.70037)). `[GUI]`
- [TDPortal](https://nrtdp.northwestern.edu/resource-software) - High-throughput, Galaxy-based top-down search system on HPC from the NRTDP, available to academic users on request. `[CLI]`
- [UniDec](https://github.com/michaelmarty/UniDec) - Bayesian deconvolution of intact-mass and ion-mobility spectra for native MS and intact protein analysis. `[GUI]` `[API]`
- [Theropod](https://github.com/clelandtp/Theropod) - STORI analysis tools for externally collected Orbitrap transients enabling charge-detection / individual-ion proteoform mass spectra ([paper](https://doi.org/10.1021/jasms.5c00328)). `[CLI]`
- [MSModDetector](https://github.com/marjanfaizi/MSModDetector) - Detects and quantifies intact-protein mass shifts from individual-ion MS (I2MS) and infers candidate PTM patterns via linear programming ([paper](https://doi.org/10.1093/bioinformatics/btae335)). `[CLI]` `[API]`
- [ClipsMS](https://github.com/loolab2020/ClipsMS) - Algorithm for assigning both terminal and internal fragment ions in top-down mass spectra to localize modifications along the protein sequence. `[CLI]`
- [Proteo-SAFARI](https://github.com/mblanzillotti/Proteo-SAFARI) - R/Shiny app for m/z-domain fragment-ion assignment from intact-protein MS/MS (including UVPD hydrogen-shift fitting) ([paper](https://doi.org/10.1021/acs.jproteome.4c00607)). `[GUI]`
- [FLASHDeconv](https://openms.de/FLASHDeconv) - Ultrafast OpenMS tool for MS1/MS2 top-down spectral and feature deconvolution with TopPIC-compatible outputs ([paper](https://doi.org/10.1016/j.cels.2020.01.003)). `[CLI]` `[GUI]`
- [FLASHApp](https://www.openms.org/FLASHApp/) - OpenMS web app for interactive top-down analysis and visualization wrapping FLASHDeconv and FLASHTnT workflows ([paper](https://doi.org/10.1002/pmic.70042)). `[GUI]`
- [TDEase](https://github.com/Computational-TDMS/TDEase) - TopPIC-oriented TDP framework with TDPipe processing and TDVis/TDVisWeb interactive proteoform visualization ([paper](https://doi.org/10.1002/pmic.70031)). `[GUI]` `[CLI]`
- [Proteoform-predictor](https://github.com/Tao-su/Proteoform-predictor) - Homology-based PTM-site transfer to expand proteoform search databases for top-down analysis of poorly annotated species ([paper](https://doi.org/10.1021/acs.jproteome.4c00943)). `[CLI]`
- [Consortium for Top-Down Proteomics (CTDP)](https://ctdp.org/) - Nonprofit community advancing proteoform analysis, standards, the Human Proteoform Project, and the Proteoform Atlas data repository.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Quantitative Proteomics

_Last Verified: Q2 2026_

> DIA, targeted (SRM/PRM), and label-based quantification. Consolidates DIA and targeted approaches; will split via the [30/10 Rule](GOVERNANCE.md#the-3010-rule) when content density warrants it.

&#x1F4D6; _Workflow:_ [Label-Free DDA](workflows/label-free-dda.md) &middot; [DIA Analysis](workflows/dia-analysis.md) _(planned)_

### DIA Tools

- [DIA-NN](https://github.com/vdemichev/DiaNN) - Automated DIA (and DDA) quantification with deep learning; 2.x adds Proteoform Confidence for peptidoform/protein-level confidence closer to DDA and PTM model fine-tuning. `[DIA]` `[Label-Free]` `[CLI]` 🐧 🪟 ([benchmark](https://doi.org/10.1021/acs.jproteome.1c00490))
- [Spectronaut](https://biognosys.com/software/spectronaut/) - Commercial DIA analysis software supporting directDIA and spectral-library workflows. `[DIA]` `[GUI]` 💰 ([benchmark](https://doi.org/10.1021/acs.jproteome.1c00490))
- [OpenSWATH](https://openms.readthedocs.io/en/latest/tutorials/knime-user-tutorial/openswath.html) - Targeted analysis of DIA and SWATH-MS data within the OpenMS ecosystem. `[DIA]` `[CLI]` ([benchmark](https://doi.org/10.1038/nbt.3685))
- [EncyclopeDIA](https://bitbucket.org/searleb/encyclopedia) - Library search engine for DIA using chromatogram and DDA-based spectral libraries. `[DIA]` `[GUI]`
- [Carafe2](https://github.com/Noble-Lab/Carafe) - Deep learning tool that builds experiment-specific in silico spectral libraries by fine-tuning RT, fragment intensity, and (for timsTOF) ion mobility models on DIA data, including native Bruker .d ([preprint](https://doi.org/10.64898/2026.03.27.714846)). `[DIA]` `[CLI]` 🧪
- [Pioneer](https://github.com/nwamsley1/Pioneer.jl) - Fast Julia CLI for spectrum-centric DIA identification and quantification with isolation-window–aware re-isotoping of Altimeter/Koina predicted libraries ([preprint](https://doi.org/10.64898/2026.02.16.706201)). `[DIA]` `[CLI]` 🧪
- [Disc-Hub](https://github.com/yuyiwen-yiyuwen/Disc_Hub) - Python package for benchmarking DIA target–decoy ML strategies (semi/fully supervised/k-fold × LDA/SVM/XGBoost/MLP) ([paper](https://doi.org/10.1093/bioadv/vbaf232)). `[DIA]` `[CLI]` `[API]`
- [DIAlignR](https://github.com/Roestlab/DIAlignR) - Retention time alignment across DIA, SWATH, PRM, and SRM runs for consistent quantification. `[DIA]` `[CLI]`
- [Calib-RT](https://github.com/chenghui03/Calib_RT) - Engine-independent nonlinear peptide retention-time calibration for DIA spectral libraries (PyPI: pycalib-rt) ([paper](https://doi.org/10.1093/bioinformatics/btae417)). `[DIA]` `[CLI]` `[API]`
- [STAVER](https://github.com/Ran485/STAVER) - Uses standardized reference DIA datasets to reduce non-biological variation and noise in large-scale hybrid spectral-library DIA quantification ([paper](https://doi.org/10.1093/bib/bbae553)). `[DIA]` `[CLI]`
- [DIA-Umpire](https://github.com/Nesvilab/DIA-Umpire) - Untargeted DIA analysis that generates pseudo-MS/MS spectra for conventional database searching. `[DIA]` `[CLI]` ([benchmark](https://doi.org/10.1038/nbt.3685))

### Targeted / SRM / PRM

- [Skyline](https://skyline.ms/) - Open-source environment for building and analyzing SRM, PRM, targeted, and DIA assays. `[Targeted]` `[DIA]` `[GUI]` 🪟 ([benchmark](https://doi.org/10.1038/nbt.3685))
- [Panorama](https://panoramaweb.org/) - Web repository and dashboard for targeted proteomics data built on Skyline documents. `[Targeted]` `[API]`
- [Avant-garde](https://github.com/SebVaca/Avant_garde) - Data-driven refinement of DIA and PRM signals by removing interfering transitions and scoring peaks. `[Targeted]` `[DIA]` `[CLI]`
- [MsTargetPeaker](https://github.com/chiyang/MsTargetPeaker) - Quality-aware MRM/PRM peak picking via deep reinforcement learning and Monte Carlo tree search, with Skyline-compatible boundaries and diagnostic reports ([paper](https://doi.org/10.1016/j.mcpro.2026.101523)). `[Targeted]` `[CLI]`
- [ProPickML](https://github.com/Ellcoy/ProPickML) - XGBoost peak picking for label-free SRM chromatograms, aimed at reducing manual validation versus mProphet-style scoring ([paper](https://doi.org/10.1021/acs.jproteome.4c00689)). `[Targeted]` `[CLI]`
- [loqculate](https://github.com/eneskemalergin/loqculate) - Command-line calculator and Python library for limits of detection and quantitation (LoD/LoQ) from DIA and targeted calibration curves, reading DIA-NN, Spectronaut, Skyline, and EncyclopeDIA outputs. `[Targeted]` `[DIA]` `[CLI]` `[API]`
- [matrix-matched_calcurves](https://github.com/lindsaypino/matrix-matched_calcurves) - Reference Python implementation of matrix-matched calibration curves for LOD/LOQ figures of merit, fitting a piecewise noise-plus-signal model with bootstrapped CV thresholds; the Pino 2020 method that loqculate reimplements ([paper](https://pubmed.ncbi.nlm.nih.gov/32037841/)). `[Targeted]` `[CLI]` 📦

### Label-Based Quantification (TMT, SILAC, iTRAQ)

> Isobaric and metabolic labeling is handled within the major suites; the entries below cover label-specific steps and statistics.

- [TMT-Integrator](https://fragpipe.nesvilab.org/) - Generates multi-level isobaric quantification reports, distributed with FragPipe. `[TMT]` `[CLI]`
- [optTMT](https://github.com/mgerault/optTMT) - R/Shiny tool that optimizes TMT channel layouts to minimize reporter-ion interference false positives ([paper](https://doi.org/10.1093/bioadv/vbaf243)). `[TMT]` `[GUI]` `[CLI]`
- [MSstatsTMT](https://github.com/Vitek-Lab/MSstatsTMT) - R/Bioconductor package for protein-level statistical analysis of TMT experiments, including thermal proteome profiling designs that trade temperatures for biological replicates ([paper](https://doi.org/10.1016/j.mcpro.2025.100999)). `[TMT]` `[CLI]`
- [isobar](https://bioconductor.org/packages/isobar) - R/Bioconductor package for iTRAQ and TMT protein and peptide quantification with statistics. `[TMT]` `[CLI]`
- Core TMT and SILAC quantification is supported by [MaxQuant](#discovery-proteomics) and [FragPipe](#discovery-proteomics).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Post-Translational Modifications

_Last Verified: Q2 2026_

> Tools and resources organized by modification type. For unrestricted (open) modification discovery, see also the search engines under [Bioinformatics & Computational Tools](#bioinformatics--computational-tools).

&#x1F4D6; _Guide:_ [PTM Analysis Strategy](guides/ptm-analysis-strategy.md) _(planned)_

### Phosphoproteomics

> Site localization, motif discovery, kinase-activity inference, and curated PTM knowledge bases.

- [PhosphoSitePlus](https://www.phosphosite.org/) - Curated knowledge base of experimentally observed phosphorylation, acetylation, ubiquitination, and methylation sites in human, mouse, and rat; free for academic and commercial use.
- [EPSD 2.0](http://epsd.biocuckoo.cn/) - Eukaryotic phosphorylation site database (~2.77M experimental p-sites in 223 species) with functional annotations and phosphopeptide provenance ([paper](https://doi.org/10.1093/gpbjnl/qzaf057)).
- [LuciPHOr2](http://luciphor2.sourceforge.net/) - Target-decoy site localization for generic modifications with false localization rate estimation from tandem MS data. `[CLI]`
- [onsite](https://github.com/bigbio/onsite) - Python package for phosphosite localization (AScore, PhosphoRS, LuciPHOr2/pyLucXor) with alanine-decoy false localization rate estimation; integrated with quantms ([preprint](https://doi.org/10.64898/2026.07.08.737157)). `[CLI]` `[API]` 🧪
- [DeepMS2-phospho](https://github.com/lmsac/DeepMS2-phospho) - Deep learning prediction of phosphopeptide fragment spectra for spectral matching-based site localization. `[CLI]`
- [PhosSight](https://github.com/YiCITI/PhosSight) - Deep learning phosphoproteomics framework (PhosDetect BiGRU detectability) for DDA rescoring/site localization and DIA library pruning ([paper](https://doi.org/10.1002/advs.75856)). `[CLI]` `[API]`
- [PhosMap](https://github.com/liuzan-info/PhosMap) - Interactive platform for quantitative phosphoproteomics (QC, DE, kinase activity, motifs, survival) from MaxQuant, Spectronaut, and DIA-NN ([paper](https://doi.org/10.1016/j.compbiomed.2024.108391)). `[GUI]` `[CLI]` 📦
- [RokaiXplorer](https://rokai.io/explorer/) - Interactive web/Shiny tool for proteomics and phosphoproteomics (DE, kinase inference via RoKAI, enrichment, deployable data browsers) ([paper](https://doi.org/10.1093/bioadv/vbae077)). `[GUI]`
- [sitereport (msproteomics)](https://github.com/tvpham/msproteomics) - MaxLFQ site- and peptide-level reporting from DIA-NN/Spectronaut phosphoproteomics outputs ([paper](https://doi.org/10.1093/bioinformatics/btae432)). `[DIA]` `[CLI]` `[API]`
- [PTMoreR](https://github.com/wangshisheng/PTMoreR) - Motif-window cross-species PTM ortholog mapper for comparative phosphoproteomics, enrichment, and kinase–substrate networks ([paper](https://doi.org/10.1016/j.crmeth.2024.100859)). `[GUI]`
- [InstaNovo-P](https://github.com/instadeepai/InstaNovo-P) - Phosphorylation-specialized InstaNovo de novo sequencer for phosphopeptide identification and site localization beyond database search ([paper](https://doi.org/10.1038/s41467-026-75138-x)). `[CLI]`
- [MoMo (MEME Suite)](https://meme-suite.org/meme/doc/momo.html) - Discovers sequence motifs associated with modification sites, reimplementing motif-x and MoDL with a web server and source code. `[CLI]`
- [KSEA App](https://github.com/casecpb/KSEA) - Kinase-Substrate Enrichment Analysis to infer changes in kinase activity from phosphoproteomics data; non-commercial use. `[CLI]`
- [KEA3](https://maayanlab.cloud/kea3/) - Web tool inferring upstream kinases whose putative substrates are enriched in a query protein or phosphoprotein list. `[API]`
- [PTM-SEA](https://github.com/broadinstitute/ssGSEA2.0) - PTM Signature Enrichment Analysis that scores site-level signatures from the PTMsigDB database. `[CLI]`

### Glycoproteomics

> Intact glycopeptide search engines and glycan structure knowledge bases.

- [pGlyco3](https://github.com/pFindStudio/pGlyco3) - Search engine for intact N- and O-glycopeptides and modified glycans with separate peptide and glycan FDR control. `[GUI]` 🪟
- [GlycReSoft](https://github.com/mobiusklein/glycresoft) - Command-line search engine for glycomics and glycoproteomics LC-MS/MS data. `[CLI]`
- [GlyComboCLI](https://github.com/Protea-Glycosciences/GlyComboCLI) - Command-line tool for combinatorial glycan composition assignment from mzML or mass lists, with Skyline/Galaxy/Docker-friendly FAIR workflows ([preprint](https://doi.org/10.64898/2026.05.13.725058)). `[CLI]` 📦 🧪
- [GRable](https://glycosmos.org/grable) - Browser tool for MS1-based Glyco-RIDGE site-specific glycoform analysis with parallel clustering and MS2 confidence scoring (v1.0) ([paper](https://doi.org/10.1016/j.mcpro.2024.100833)). `[GUI]`
- [GlycoGenius](https://github.com/LoponteHF/GlycoGenius_GUI) - GUI/CLI for high-throughput LC/CE-MS(/MS) glycomics composition identification, quantification, MS2 annotation, and SNFG cartoons ([paper](https://doi.org/10.1038/s41467-025-65265-2)). `[GUI]` `[CLI]`
- [NovoGlyco](https://sourceforge.net/projects/novoglycox/) - Untargeted prokaryotic glycoproteomics platform combining oxonium discovery, sequence-tag matching, and mass-offset binning from shotgun MS data ([preprint](https://doi.org/10.64898/2026.04.15.718822)). `[GUI]` 🧪
- [Oxonium Browser](https://sourceforge.net/projects/oxoniumbrowserx/) - GUI for untargeted oxonium-ion discovery in high-resolution shotgun proteomics, especially rare prokaryotic sugar fragments; companion to NovoGlyco ([preprint](https://doi.org/10.64898/2026.04.15.718822)). `[GUI]` 🪟 🧪
- [GlycoDiveR](https://github.com/riley-research/GlycoDiveR) - Modular R framework that imports FragPipe, Byonic, pGlyco, Perseus, and MSstats glycoproteomics outputs into >25 publication-ready visualizations ([preprint](https://doi.org/10.64898/2026.03.21.713336)). `[CLI]` `[API]` 🧪
- [GlyCounter](https://github.com/riley-research/GlyCounter) - Windows GUI that extracts oxonium, Y-type, and custom glycan ions from Thermo .raw/mzML without requiring glycopeptide IDs ([paper](https://doi.org/10.1016/j.mcpro.2025.101085)). `[GUI]` 🪟
- [glycoTraitR](https://github.com/matsui-lab/glycoTraitR) - R package that converts pGlyco3/Glyco-Decipher GPSMs into composition and structural glycan traits (site/protein SummarizedExperiment) for differential analysis ([preprint](https://doi.org/10.64898/2025.12.16.694754)). `[CLI]` `[API]` 🧪
- [GP-Plotter](https://github.com/DICP-1809/GP-Plotter) - GUI for annotated MS/MS spectral visualization with strong glycan-ion support for intact glycopeptides; also bundled in Glyco-Decipher ([paper](https://doi.org/10.1093/gpbjnl/qzae069)). `[GUI]`
- [StrucGP](https://github.com/Sun-GlycoLab/StrucGP) - Database-independent search engine for structural interpretation of N-glycans on intact glycopeptides. `[GUI]` 🪟
- [StrucGAP](https://github.com/Sun-GlycoLab/StrucGAP) - Python platform for downstream structural and site-specific glycoproteomics analysis, covering preprocessing, quantification, network visualization, and annotation across multiple search engines. `[CLI]` `[API]`
- [Byonic](https://www.proteinmetrics.com/products/byonic) - Commercial search engine for peptide, protein, and glycopeptide identification supporting wide PTM searches. `[GUI]` 💰
- [pGlycoQuant](https://github.com/Power-Quant/pGlycoQuant) - Quantification tool for intact glycopeptides that works with pGlyco3 and other search results. `[CLI]`
- [GlyTouCan](https://glytoucan.org/) - International glycan structure repository that assigns globally unique accession numbers to registered glycans.
- [GlyConnect](https://glyconnect.expasy.org/) - Database of glycosylation sites, glycan structures, and associated proteins on the SIB ExPASy portal.
- [DQGlyco explorer](https://apps.embl.de/glycoapp/) - Interactive browser for deep quantitative N-glycoproteomics mouse and human datasets from the DQGlyco study ([paper](https://doi.org/10.1038/s41594-025-01485-w)). `[GUI]`
- [GlyGen](https://www.glygen.org/) - Integrated knowledge base unifying glycan, glycoprotein, and glycosylation data from multiple sources.
- [GlyCosmos](https://glycosmos.org/) - Web portal integrating glycan structures, glycogenes, glycoproteins, pathways, and related repositories.
- [GlycoEnzDB](https://www.virtualglycome.org/glycoenzdb/) - Database of ~403 human glycosylation enzymes (GlycoEnzOnto) with pathway maps, expression, and CRISPR aids ([paper](https://doi.org/10.1093/glycob/cwaf074)).

> Glyco workflows are also built into [FragPipe](#discovery-proteomics) (MSFragger-Glyco) and [MetaMorpheus](#pipelines--frameworks) (O-Pair Search).

### Ubiquitination & Other PTMs

> Open-search modification characterization and cross-modification reference databases.

- [PTM-Shepherd](https://github.com/Nesvilab/PTM-Shepherd) - Characterizes and summarizes PTM profiles from open searches using localization, spectral similarity, retention time, and modification rates. `[CLI]`
- [OpenSpec](https://github.com/BUAA-LiuLab/OpenSpec) - Windows GUI workflow that deconvolutes Orbitrap Astral DIA into pseudo-MS/MS spectra for DDA open search of unexpected modifications ([paper](https://doi.org/10.1021/acs.analchem.5c03055)). `[DIA]` `[GUI]` 🪟
- [rDeamidation](https://github.com/tsutatsuta/rdeamidation) - R port of MaxQuant evidence-based N/Q deamidation rate calculation with bootstrap confidence intervals (useful for paleoproteomics and sample QC). `[CLI]`
- [MSstatsPTM](https://bioconductor.org/packages/MSstatsPTM) - R/Bioconductor package for statistical analysis of PTM-site abundance that adjusts for changes in overall protein levels, supporting DDA, DIA, SRM, and TMT data. `[CLI]`
- [PEIMAN2](https://cran.r-project.org/package=PEIMAN2) - R package for UniProt-based PTM singular enrichment (SEA) and protein-set enrichment (PSEA) with matching across protein lists ([paper](https://doi.org/10.1002/pmic.202400238)). `[CLI]` `[API]`
- [ProteoMeter](https://github.com/PNNL-Predictive-Phenomics/ProteoMeter) - Python pipeline that maps multi-PTM and limited-proteolysis (LiP-MS) peptide quantitation to residue/site resolution with abundance correction and unified coordinates. `[CLI]` `[API]`
- [CysNet](https://github.com/JamesCobley/CysNet) - Infers cysteine redox proteoform (oxiform) constraints from bottom-up redox MS site marginals with optional copy-number scaling ([preprint](https://doi.org/10.64898/2026.07.06.736853)). `[CLI]` `[GUI]` `[API]` 🧪
- [CysDB](https://backuslab.shinyapps.io/cysdb/) - Curated human cysteine chemoproteomics atlas (~62k sites from nine quantitative MS studies) with ligandability, reactivity, and disease annotations ([paper](https://doi.org/10.1016/j.chembiol.2023.04.004)). `[GUI]`
- [dbPTM](https://biomics.lab.nycu.edu.tw/dbPTM/) - Integrated database of experimentally verified and predicted PTM sites with functional and structural annotation.
- [O-GlcNAcAtlas](https://oglcnac.org/atlas/) - Curated database of experimentally identified protein O-GlcNAc sites with site-specific quantification across species and conditions ([paper](https://doi.org/10.1016/j.jmb.2025.169033)).
- [StrucPTM](https://github.com/HanyangBISLab/StrucPTM) - Database of PTM residues validated at atom level in PDB structures, with UniProt mapping and homolog-based conformational comparison ([paper](https://doi.org/10.1093/bioinformatics/btag190)).
- [iPTMnet](https://research.bioinformatics.udel.edu/iptmnet/) - Bioinformatics resource integrating PTM sites, modifying enzymes, and substrate relationships for systems biology.
- [Unimod](https://www.unimod.org/) - Reference of protein modifications and their mass shifts for mass spectrometry, maintained with the HUPO-PSI.

> Unrestricted modification discovery is provided by [MSFragger](#identification), [pFind](#discovery-proteomics) (Open-pFind), and [MetaMorpheus](#pipelines--frameworks) (G-PTM-D); ubiquitin diGly remnant profiling is supported within [MaxQuant](#discovery-proteomics) and [FragPipe](#discovery-proteomics).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Single-Cell Proteomics

_Last Verified: Q2 2026_

> Tools and resources for single-cell and low-input proteomics. Entries require documentation and at least one published use case.

&#x1F4D6; _Guide:_ [Single-Cell Best Practices](guides/single-cell-best-practices.md) _(planned)_

- [scp](https://bioconductor.org/packages/scp) - Bioconductor package for processing and analyzing mass spectrometry-based single-cell proteomics data. `[CLI]`
- [SCeptre](https://github.com/bfurtwa/SCeptre) - Python package that extends Scanpy to analyze multiplexed single-cell proteomics data. `[CLI]`
- [QFeatures](https://bioconductor.org/packages/QFeatures) - R/Bioconductor infrastructure for managing quantitative features across PSM, peptide, and protein levels; the data backbone the scp package builds on. `[API]`
- [scpdata](https://bioconductor.org/packages/scpdata) - R/Bioconductor data package distributing standardized, annotated mass spectrometry single-cell proteomics datasets formatted with the scp structure. `[API]`
- [DART-ID](https://github.com/SlavovLab/DART-ID) - Bayesian retention-time alignment that boosts confident peptide identifications in low-input and single-cell samples, increasing data points by 30-50% at 1% FDR. `[CLI]`
- [NIFty](https://github.com/PayneLab/nifty) - Top-scoring-pairs classification pipeline for single-cell proteomics that handles missing values without imputation and avoids circular analysis / batch pitfalls ([preprint](https://doi.org/10.64898/2026.03.06.710179)). `[CLI]` 🧪
- [SoftHybrid](https://github.com/YixinShiProteomics/softHybridImpute) - Unsupervised R imputation that soft-weights Random Forest (MAR) and MinProb (MNAR) for single-cell and low-input proteomics ([preprint](https://doi.org/10.64898/2026.01.13.699212)). `[CLI]` `[API]` 🧪
- [PSCS](https://pscs.xods.org/) - No-code web platform for designing, running, and publishing shareable single-cell omics analysis pipelines with data and interactive results ([paper](https://doi.org/10.1021/acs.jproteome.5c00178)). `[GUI]`
- [SCP resources (Slavov Lab)](https://scp.slavovlab.net/) - Community hub for single-cell proteomics methods, protocols, datasets, and reporting guidelines.
- [Single-Cell Proteomics Conference](https://single-cell.net/) - Annual conference with an open archive of recorded talks and community guidelines.
- [Focus on single-cell proteomics (Nature Methods)](https://www.nature.com/collections/bdfhafhdeb) - Curated Nature Methods collection of articles on single-cell proteomics methods, challenges, and applications.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Bioinformatics & Computational Tools

_Last Verified: Q2 2026_

> **The backbone of this list.** Computational tools for proteomics data analysis, organized by function. Capability tags help you find what works with your data and platform.

&#x1F4D6; _Workflow:_ [Label-Free DDA](workflows/label-free-dda.md)

**Essential tools** (see full entries in the relevant sections):

- [MaxQuant](https://maxquant.org/) - Quantitative proteomics software for analyzing large mass spectrometric data sets. `[DDA]` `[Label-Free]` `[TMT]` `[SILAC]` &#x1F5A5;&#xFE0F;
- [MSFragger](https://msfragger.nesvilab.org/) - Fragment-ion indexing database search engine for peptide identification. `[DDA]` `[DIA]` `[CLI]`
- [DIA-NN](https://github.com/vdemichev/DiaNN) - Deep neural network-based software for DIA and DDA proteomics (2.x Proteoform Confidence). `[DIA]` `[DDA]` `[Label-Free]` `[CLI]`

<details>
<summary><b>Sub-section index</b> (click to expand)</summary>
<br>

| Sub-section                                      | What it covers                                                                   |
| ------------------------------------------------ | -------------------------------------------------------------------------------- |
| [Identification](#identification)                | Search engines, spectral libraries, rescoring                                    |
| [Quantification](#quantification)                | Label-free, isobaric, metabolic labeling tools                                   |
| [Statistical Analysis](#statistical-analysis)    | Differential expression, imputation, normalization, batch correction, enrichment |
| [Visualization](#visualization)                  | Plots, interactive dashboards, spectrum viewers                                  |
| [Quality Control](#quality-control)              | Run monitoring, QC reports, raw-file diagnostics                                 |
| [Pipelines & Frameworks](#pipelines--frameworks) | End-to-end analysis platforms                                                    |
| [Cloud & HPC](#cloud--hpc)                       | nf-core, Galaxy, Nextflow/Snakemake tooling                                      |

</details>

### Identification

- [MSFragger](https://msfragger.nesvilab.org/) - Fragment-ion indexing database search engine for closed and open (mass-tolerant) peptide identification. `[DDA]` `[DIA]` `[CLI]`
- [Comet](https://uwpr.github.io/Comet/) - Open-source tandem mass spectrometry database search engine derived from the SEQUEST algorithm. `[DDA]` `[CLI]`
- [Sage](https://github.com/lazear/sage) - Cross-platform search engine in Rust with built-in quantification, rescoring, and FDR control. `[DDA]` `[CLI]` 🐧 🪟 🍎
- [Dear-PSM](https://github.com/jianweishuai/Dear-PSM) - Deep learning search engine for full-database PSM matching without precursor mass filtering and up to 20 variable modifications per peptide ([paper](https://doi.org/10.1002/smmd.20240014)). `[DDA]` `[CLI]`
- [QuickSearchProt](https://github.com/barsnes-group/QuickSearchProt) - GUI tool that auto-selects Sage and X!Tandem search parameters from a representative MGF subset and exports SearchGUI-compatible `.par` files ([paper](https://doi.org/10.1021/acs.jproteome.5c00641)). `[DDA]` `[GUI]`
- [Percolator](http://percolator.ms/) - Semi-supervised post-processor that rescores peptide-spectrum matches and controls FDR. `[CLI]`
- [Tesorai Search](https://console.tesorai.com/) - Cloud deep-learning PSM scoring from full spectra and peptide sequences without Percolator/decoy-trained rescoring; free academic tier ([preprint](https://doi.org/10.1101/2024.08.19.606805)). `[GUI]` 💰 🧪
- [mokapot](https://github.com/wfondrie/mokapot) - Flexible Python reimplementation of the Percolator rescoring algorithm. `[CLI]` `[API]`
- [MS-GF+](https://github.com/MSGFPlus/msgfplus) - Database search engine that uses a generating-function scoring approach and supports many instrument types and fragmentation methods. `[DDA]` `[CLI]`
- [MSAndrea](https://github.com/hgb-bin-proteomics/MSAndrea) - Open modification search engine that resolves combinations of up to four Unimod modifications with site assignments at the PSM level using MS Amanda scoring ([preprint](https://doi.org/10.64898/2026.03.27.714851)). `[DDA]` `[CLI]` 🧪
- [deTELpy](https://git.mpi-cbg.de/tothpetroczylab/detelpy) - Python pipeline (MSFragger open search) to detect amino-acid substitutions and estimate translation-error rates from MS datasets ([paper](https://doi.org/10.1093/bioinformatics/btae424)). `[CLI]` `[API]`
- [SpecPeptidOMS](https://github.com/bibs-lab/SpecPeptidOMS) - Java tool that aligns MS/MS spectra to whole undigested proteomes for non-tryptic/peptidomics identification and open-modification search ([paper](https://doi.org/10.1021/acs.jproteome.4c00870)). `[DDA]` `[CLI]`
- [Crux](https://crux.ms/) - Cross-platform toolkit bundling the Tide search engine, Percolator, and label-free quantification. `[DDA]` `[CLI]` 🐧 🪟 🍎
- [THE GPM](https://www.thegpm.org/) - Community portal for X!Tandem-based proteomics search and validation; note that GPMDB queries have been blocked for US IP addresses since February 2025. `[GUI]`
- [SPROUTS_DB](https://doi.org/10.1002/pmic.70128) - Contaminant FASTA (~1,288 FBS/serum and lab proteins) for secretome and extracellular-vesicle searches; FASTA in paper SI, raw data at PRIDE PXD044137.
- [UniScore](https://github.com/jPOST-tools/UniScorePrograms20241016) - Lightweight product-ion annotation score that unifies multi-engine DDA PSMs (Comet, X!Tandem, Mascot, MaxQuant) with target–decoy FDR, used in jPOST reanalysis ([paper](https://doi.org/10.1016/j.mcpro.2025.101010)). `[CLI]`
- [Grape-Pi](https://github.com/FDUguchunhui/GrapePi) - Graph neural network that uses PPI message passing to improve protein-level identification calls from MS pipeline scores ([paper](https://doi.org/10.1093/bioadv/vbaf095)). `[CLI]` `[API]`
- [PeptideForest](https://github.com/peptideforest/peptideForest) - Semisupervised random-forest rescoring that integrates PSMs from multiple DDA search engines (Ursgal-compatible) ([paper](https://doi.org/10.1021/acs.jproteome.4c00686)). `[DDA]` `[CLI]` `[API]`
- [ProtGraph](https://github.com/mpc-bioinformatics/ProtGraph) - Builds UniProt feature graphs (isoforms/variants/cleavage) and exports precursor-specific FASTA to expand MS peptide search space ([paper](https://doi.org/10.1093/bib/bbae671)). `[CLI]` `[API]`

### Quantification

- [MaxQuant](https://maxquant.org/) - See [Discovery Proteomics](#discovery-proteomics) for the full entry. Andromeda-based suite with label-free, SILAC, and TMT quantification.
- [IonQuant](https://github.com/Nesvilab/IonQuant) - Label-free and isobaric quantification with match-between-runs and FDR control, used within the FragPipe ecosystem. `[Label-Free]` `[TMT]` `[CLI]`
- [FlashLFQ](https://github.com/smith-chem-wisc/FlashLFQ) - Label-free quantification engine with match-between-runs, usable standalone or within MetaMorpheus. `[Label-Free]` `[CLI]`
- [directLFQ](https://github.com/MannLabs/directlfq) - Label-free protein quantification using a ratio-based algorithm that scales linearly to very large sample cohorts. `[Label-Free]` `[CLI]` `[API]`
- [Triqler](https://github.com/statisticalbiotechnology/triqler) - Probabilistic model that propagates identification and quantification error into protein-level fold changes. `[CLI]`
- [Alpaca](https://github.com/borfebor/alpaca_proteomics) - Python pipeline (library + GUI) for absolute label-free protein abundance mining from unprocessed LFQ tables, including enriched-fraction designs ([paper](https://doi.org/10.1002/pmic.202400417)). `[Label-Free]` `[CLI]` `[GUI]` `[API]`
- [ibaqpy](https://github.com/bigbio/ibaqpy) - Scalable iBAQ / rIBAQ / ppb absolute quantification from quantms.io feature tables with SDRF-driven normalization and batch correction ([paper](https://doi.org/10.1016/j.jprot.2025.105440)). `[CLI]` `[API]`

### Statistical Analysis

- [MSstats](https://msstats.org/) - R/Bioconductor package for statistical relative quantification across label-free, DIA, and labeled experiments. `[CLI]`
- [MSstatsWeightedSummary](https://github.com/Vitek-Lab/MSstatsWeightedSummary) - R package for weighted protein-level summarization of shared-peptide clusters, compatible with MSstatsTMT ([paper](https://doi.org/10.1093/bioinformatics/btaf046)). `[TMT]` `[CLI]` `[API]`
- [MSstatsResponse](https://bioconductor.org/packages/MSstatsResponse/) - Semi-parametric dose-response modeling for chemoproteomics (drug–protein interaction detection and IC50 estimation) that works with MSstats/MSstatsTMT summaries. `[CLI]`
- [DEqMS](https://bioconductor.org/packages/DEqMS) - Differential expression analysis that models PSM-count-dependent variance in quantitative proteomics. `[CLI]`
- [LimROTS](https://bioconductor.org/packages/LimROTS) - Bioconductor hybrid of limma empirical Bayes and ROTS reproducibility-optimized ranking for differential abundance in MS proteomics ([paper](https://doi.org/10.1093/bioinformatics/btaf570)). `[CLI]` `[API]`
- [DEprot](https://github.com/sebastian-gregoricchio/DEprot) - R package for LFQ proteomics normalization, serial MNAR-aware imputation, and differential expression, aimed at enrichment and knockout designs ([paper](https://doi.org/10.1093/nargab/lqag015)). `[CLI]` `[API]`
- [ProtE](https://github.com/theomargel/ProtE/) - Single-function R package (“Proteomics Eye”) for label-free MaxQuant/DIA-NN/Proteome Discoverer tables through QC, imputation, pairwise DE, and plots ([paper](https://doi.org/10.1002/prca.70037)). `[CLI]` `[API]`
- [QuickProt](https://github.com/OmarArias-Gaguancela/QuickProt) - Google Colab notebooks for downstream QC, statistics, and visualization of DIA-NN and Skyline PRM result tables ([paper](https://doi.org/10.1002/pmic.70038)). `[DIA]` `[GUI]`
- [PROTRIDER](https://github.com/gagneurlab/PROTRIDER) - Conditional autoencoder for protein abundance outlier calling from MS proteomics matrices with Student-t calibrated residuals ([paper](https://doi.org/10.1093/bioinformatics/btaf628)). `[CLI]` `[API]`
- [PLSKO](https://github.com/guannan-yang/PLSKO) - Partial least squares knockoff generator for FDR-controlled variable selection across omics matrices, including proteomics ([paper](https://doi.org/10.1093/bioinformatics/btaf475)). `[CLI]` `[API]`
- [RAPDOR](https://github.com/domonik/RAPDOR) - Non-parametric Jensen–Shannon/ANOSIM analysis of gradient and spatial proteomics redistribution profiles ([paper](https://doi.org/10.1038/s41467-025-64086-7)). `[CLI]` `[API]`
- [OMEx (Omics Molecule Extractor)](https://mdoa-tools.bi.denbi.de/omex/home) - Web app for selecting small multi-marker biomarker panels from large omics matrices via diagonal LDA with filter/wrapper feature selection ([paper](https://doi.org/10.1021/acs.jproteome.5c00176)). `[GUI]`
- [limma](https://bioconductor.org/packages/limma) - Linear-models package for differential expression, originally developed for microarrays and applicable to proteomics intensity data. `[CLI]`
- [Perseus](https://maxquant.net/perseus/) - Graphical platform for downstream statistical analysis of proteomics matrices. `[GUI]` 🪟
- [ProteoSign v2](https://bioinformatics.med.uoc.gr/ProteoSign/) - Web/Docker LIMMA differential expression for MaxQuant and Proteome Discoverer tables with enrichment and publication-ready plots ([paper](https://doi.org/10.1093/nar/gkab329)). `[GUI]` 📦
- [MAGMa](https://github.com/shg018/MAGMa) - Differential expression for TMT/SILAC proteomics aimed at subtle abundance shifts, with volcano and network plots ([preprint](https://doi.org/10.1101/2024.06.24.600424)). `[GUI]` 🧪
- [msqrob2](https://bioconductor.org/packages/msqrob2) - Robust linear mixed model framework for differential abundance, including missing-data-aware workflows. `[CLI]`
- [msqrob2PTM](https://github.com/statOmics/msqrob2PTMpaper) - msqrob2/QFeatures workflow for differential abundance and differential usage at the PTM and peptidoform level (vs parent-protein confounding) ([paper](https://doi.org/10.1016/j.mcpro.2023.100708)). `[CLI]`
- [proDA](https://github.com/const-ae/proDA) - Differential abundance analysis with a probabilistic dropout model that handles missing values without imputation. `[CLI]`
- [protti](https://github.com/jpquast/protti) - R package for quality control and analysis of bottom-up and LiP-MS data, working with output from Spectronaut, MaxQuant, Proteome Discoverer, and Skyline. `[CLI]`
- [HarmonizR](https://github.com/HSU-HPC/HarmonizR) - R package for batch-effect correction across independent proteomics datasets; it splits the matrix into sub-matrices with enough overlap to run ComBat or limma despite missing values, then reassembles the corrected result ([paper](https://doi.org/10.1038/s41467-022-31007-x)). `[API]`
- [omicsGMF](https://bioconductor.org/packages/omicsGMF) - Bioconductor matrix-factorization toolkit that jointly performs dimensionality reduction, batch/covariate correction, and missing-value imputation for bulk and single-cell proteomics ([paper](https://doi.org/10.1038/s41467-026-73402-8)). `[CLI]` `[API]`
- [HarmonizePy](https://github.com/LangeLab/HarmonizePy) - Pure-Python port of the HarmonizR approach (ComBat and limma) with structural-missingness handling, batch sorting, and blocking, validated against the R references and requiring no R runtime. `[CLI]` `[API]`
- [OBC (Omics Batch Correct)](https://zhljude.shinyapps.io/OBC-app/) - Shiny pipeline for MS proteomics/metabolomics preprocessing and ComBat batch correction with dual-tier QC (PCA/UMAP/PVCA plus differential-molecule checks) ([paper](https://doi.org/10.1093/gpbjnl/qzag033)). `[GUI]`
- [BioTrendFinder](https://cphbat.shinyapps.io/biotrendfinder/) - Interactive web tool that finds molecular trendlines in bulk proteomics/transcriptomics via sample ranking and links them to STRING and ontology modules ([preprint](https://doi.org/10.64898/2026.04.12.717932)). `[GUI]` 🧪
- [SQuAPP](https://github.com/LangeLab/SQuAPP) - Shiny application for streamlined analysis and visual comparison across multiple levels of proteomics data (peptide, protein, and PTM). `[GUI]`
- [TraianProt](https://github.com/SamueldelaCamaraFuentes/TraianProt) - R/Shiny downstream analysis for wide-format quantitative proteomics (MaxQuant, MSFragger, DIA-NN, Proteome Discoverer), including filtering, differential testing, enrichment, and STRING networks. `[GUI]` `[CLI]`
- [DiaReport](https://github.com/Gevaert-Lab/diareport) - R package for DIA-NN differential expression (MSqRob2 / QFeatures) that emits reproducible interactive Quarto HTML reports for protein- and precursor-level designs. `[DIA]` `[CLI]`
- [SpectroPipeR](https://github.com/stemicha/SpectroPipeR) - R pipeline for post-Spectronaut DIA analysis (normalization, MaxLFQ/iBAQ, ROPECA stats, interactive HTML reports) ([paper](https://doi.org/10.1093/bioinformatics/btaf086)). `[DIA]` `[CLI]`
- [prolfquapp](https://github.com/prolfqua/prolfquapp) - Command-line interface to the [prolfqua](https://github.com/fgcz/prolfqua) R package for differential expression and QC reports from DIA-NN, MaxQuant, FragPipe, and Spectronaut outputs ([paper](https://doi.org/10.1021/acs.jproteome.4c00911)). `[CLI]` 📦
- [QProMS](https://github.com/ieoresearch/QProMS) - Shiny app for label-free quantitative proteomics downstream analysis (MaxQuant, FragPipe, Spectronaut, DIA-NN, AlphaPept) with mixed missing-value imputation and exportable reports. `[GUI]` `[Label-Free]`
- [ProteoArk](https://ciods.in/proteoark/) - Web/Docker platform for postprocessing MaxQuant, Proteome Discoverer, and MSFragger results (LFQ/SILAC/TMT) with DE, enrichment, and publication-ready plots ([paper](https://doi.org/10.1021/acs.jproteome.4c00556)). `[GUI]` 📦
- [Manchester Proteome Profiler (MPP)](https://mpp.sbs.manchester.ac.uk/) - Shiny platform for quantitative proteomics downstream analysis (MaxQuant, FragPipe, Proteome Discoverer) including dual-dataset comparison and SAINTexpress for AP-MS / proximity labeling. `[GUI]`
- [JUMPshiny](https://jumpshiny.genenetwork.org/) - GeneNetwork R/Shiny platform for isobaric and label-free quantitative proteomics (experimental design, QC, batch normalization, differential expression, enrichment); local install for large datasets ([paper](https://doi.org/10.1002/pmic.70061)). `[GUI]`
- [OncoProExp](https://oncopro.cs.ut.ee/) - Shiny platform for CPTAC cancer proteomics and phosphoproteomics (preprocessing, DE, survival, ML+SHAP); Docker/local deploy available ([paper](https://doi.org/10.1016/j.csbj.2025.08.038)). `[GUI]` 📦
- [QuEStVar](https://github.com/eneskemalergin/QuEStVar) - Python package for paired equivalence and difference testing across proteomics feature tables; it pairs a standard difference test with a TOST equivalence test so a non-significant result is reported as explicit equivalence rather than assumed, and adds CV filtering, multiple-testing correction, power analysis, and antler plots ([paper](https://doi.org/10.1021/acs.jproteome.4c00131)). `[CLI]` `[API]`
- [ProteoForge](https://github.com/eneskemalergin/ProteoForge) - Python package for differential proteoform discovery from bottom-up proteomics, grouping peptides that diverge from their protein siblings into differential proteoform units through robust discordance modeling (RLM/WLS) and Ward clustering ([paper](https://doi.org/10.1021/acs.jproteome.5c01235)). `[API]`
- [clusterProfiler](https://github.com/YuLab-SMU/clusterProfiler) - Enrichment and GSEA tool with visualization for interpreting protein and gene lists across many ontologies and species. `[API]`
- [fgsea](https://bioconductor.org/packages/fgsea) - R/Bioconductor package for preranked gene set enrichment analysis that estimates low enrichment p-values using a multilevel Monte Carlo scheme. `[CLI]`
- [PEANUT](https://peanut.cs.tau.ac.il/) - Web tool for pathway enrichment that propagates preranked gene/protein scores through PPI networks before enrichment testing ([paper](https://doi.org/10.1093/bioinformatics/btaf410)). `[GUI]`
- [pQTLtools](https://github.com/jinghuazhao/pQTLtools) - R toolkit for protein QTL / GWAS analysis (Manhattan/QQ, cis–trans classification, colocalization, MR) with peptide-level helpers and companion panels spanning SWATH-MS and affinity platforms. `[CLI]` `[API]`

### Visualization

- [Cytoscape](https://cytoscape.org/) - Platform for visualizing molecular interaction networks and integrating them with expression data. `[GUI]`
- [spectrum_utils](https://github.com/bittremieux/spectrum_utils) - Python package for processing and visualizing tandem mass spectra. `[API]`
- [PDV](https://github.com/wenbostar/PDV) - Graphical viewer for proteomics data including spectra, chromatograms, and identification results. `[GUI]`
- [IPSA (Interactive Peptide Spectral Annotator)](https://github.com/coongroup/IPSA) - Web-based annotator that generates interactive, exportable visualizations of peptide tandem mass spectra. `[GUI]`
- [Annotator](https://github.com/snijderlab/annotator) - Interactive desktop spectrum annotator for complex ProForma peptidoforms spanning bottom-up, middle-down, top-down, cross-linking, and glycopeptides ([paper](https://doi.org/10.1021/acs.analchem.5c02832)). `[GUI]`
- [Quetzal](https://proteomecentral.proteomexchange.org/quetzal/) - Web/API peptide fragment-ion annotator using the PSI mzPAF standard, with publication-quality figures ([paper](https://doi.org/10.1021/acs.jproteome.5c00092)). `[GUI]` `[API]`
- [ComplexHeatmap](https://github.com/jokergoo/ComplexHeatmap) - R/Bioconductor package for generating annotated heatmaps, applied to proteomics expression matrices. `[API]`
- [MassSpectrum Analyzer](https://github.com/Kristian-Karlic/MassSpectrum-Analyzer) - Interactive desktop tool for custom fragment annotation and modification-focused rescoring of PSMs from MSFragger, MaxQuant, MetaMorpheus, and related engines ([preprint](https://doi.org/10.64898/2026.06.22.733873)). `[GUI]` 🧪
- [HPAanalyze](https://bioconductor.org/packages/HPAanalyze/) - R/Bioconductor package to download, subset, and visualize Human Protein Atlas tissue, pathology, and subcellular data (complements the HPA website). `[CLI]` `[API]`
- [UniprotR](https://cran.r-project.org/package=UniprotR) - R package to retrieve UniProtKB annotations for accession lists and plot GO, physicochemical, chromosomal, and network summaries for proteomics results. `[CLI]` `[API]`
- [PTMOverlay](https://github.com/evergreen700/PTMOverlay) - Snakemake pipeline that overlays pepXML PTM sites onto KEGG/MUSCLE multi-species protein alignments to visualize evolutionary conservation ([preprint](https://doi.org/10.64898/2026.02.03.703592)). `[CLI]` 📦 🧪
- [PepMapViz](https://github.com/Genentech/PepMapViz) - R/Shiny toolkit for mapping MS peptides onto protein sequences with domains, mutations, and PTM highlights across conditions ([paper](https://doi.org/10.1093/bioinformatics/btaf404)). `[GUI]` `[API]`
- [ProteoPlotter](https://github.com/JGM-Lab-UoG/ProteoPlotter) - Executable R/Shiny companion to Perseus for volcano, PCA, Venn/UpSet, dynamic-range, and 1D-annotation heatmap figures ([paper](https://doi.org/10.1021/acs.jproteome.4c00963)). `[GUI]` 🪟
- [PTMVision](https://ptmvision-tuevis.cs.uni-tuebingen.de/) - Interactive web server for exploring MS-derived PTM landscapes (MaxQuant, MSFragger, Spectronaut, Sage, ionbot, mzIdentML/CSV) with sequence and 3D/contact-map views ([paper](https://doi.org/10.1021/acs.jproteome.4c00679)). `[GUI]` 📦
- [Limelight](https://limelight-ms.org/) - Web platform for sharing and visualizing full-stack DDA proteomics results (PSMs through proteins/modifications) across search pipelines ([paper](https://doi.org/10.1021/acs.jproteome.4c00968)). `[DDA]` `[GUI]`
- [pyOpenMS-viz](https://github.com/OpenMS/pyopenms_viz) - Pandas DataFrame plotting API for MS spectra, chromatograms, mobilograms, and peak maps with matplotlib/bokeh/plotly backends ([paper](https://doi.org/10.1021/acs.jproteome.4c00873)). `[API]`

### Quality Control

- [RawTools](https://github.com/kevinkovalchik/RawTools) - Extraction of QC metrics and quantification information directly from Thermo raw files. `[CLI]`
- [rawrr](https://bioconductor.org/packages/rawrr) - R package for reading Thermo raw files directly for diagnostics and QC. `[CLI]`
- [PTXQC](https://github.com/cbielow/PTXQC) - R package generating quality control reports from MaxQuant output. `[CLI]`
- [PeakQC](https://github.com/pnnl/IonToolPack) - Omics-agnostic automated QC of raw MS runs (proteomics/metabolomics/lipidomics) via PCA and ion metrics without requiring IDs; ships in IonToolPack ([paper](https://doi.org/10.1021/jasms.4c00146)). `[GUI]`
- [rawDiag](https://github.com/fgcz/rawDiag) - R package producing diagnostic plots from raw files to support rational LC-MS method optimization. `[CLI]`
- [MSstatsQC](https://bioconductor.org/packages/MSstatsQC/) - Longitudinal system-suitability and QC monitoring with statistical process control charts and an optional supervised ML (MSstatsQC-ML) module for run failure prediction. `[CLI]` `[GUI]`
- [LAMPrEY](https://github.com/LewisResearchGroup/LAMPrEY) - Docker-based QC pipeline server for large-cohort quantitative proteomics that automates MaxQuant and RawTools processing with a web dashboard and API ([preprint](https://doi.org/10.64898/2026.05.06.722826)). `[GUI]` `[API]` `[TMT]` 📦 🧪
- [diagFDR](https://cran.r-project.org/package=diagFDR) - R package for verifiable target–decoy FDR diagnostics (scope, calibration, and stability) across MaxQuant, DIA-NN, and mzIdentML outputs ([preprint](https://doi.org/10.64898/2026.04.16.718468)). `[CLI]` 🧪
- [pmultiqc](https://pmultiqc.quantms.org/) - MultiQC plugin for metadata-oriented proteomics QC reports (quantms, MaxQuant, DIA-NN, FragPipe, mzIdentML, ProteoBench) with SDRF sample grouping ([paper](https://doi.org/10.1016/j.mcpro.2026.101530)). `[CLI]`
- [ProteoGyver](https://github.com/varjolab/Proteogyver) - Lightweight Docker web platform for rapid MS proteomics QC and preliminary DE/interactomics (SAINT) analysis ([paper](https://doi.org/10.1093/bioinformatics/btag050)). `[GUI]` 📦
- [SpecQuality](https://github.com/alkayadav10/SpecQuality) - MS/MS spectral quality scores (SQS) from ten features via geometric mean or XGBoost for pre-search triage and post-search PSM validation ([paper](https://doi.org/10.1021/jasms.5c00168)). `[CLI]`
- [iDIA-QC](https://github.com/guomics-lab/iDIA-QC) - GUI for AI quality control of DIA raw files (Orbitrap, TripleTOF, timsTOF) using msConvert/DIA-NN metrics ([paper](https://doi.org/10.1038/s41467-024-54871-1)). `[DIA]` `[GUI]`
- [CAT-APP](https://www.bloodecosystem.com/tools/CAT-APP/) - Web platform that detects and corrects erythrocyte/platelet/coagulation contamination in plasma proteomics matrices ([preprint](https://doi.org/10.1101/2025.07.08.663798)). `[GUI]` 🧪

### Pipelines & Frameworks

- [FragPipe](https://fragpipe.nesvilab.org/) - See [Discovery Proteomics](#discovery-proteomics). GUI pipeline integrating MSFragger, IonQuant, and Philosopher.
- [OpenMS](https://www.openms.de/) - Open-source C++/Python framework with composable tools for building MS workflows. `[CLI]` `[API]` 🐧 🪟 🍎
- [MetaMorpheus](https://github.com/smith-chem-wisc/MetaMorpheus) - Search and analysis platform supporting PTM discovery (G-PTM-D), calibration, and quantification. `[DDA]` `[GUI]` `[CLI]`
- [pyteomics](https://github.com/levitsky/pyteomics) - Python framework for reading proteomics data formats and performing common computations. `[API]`
- [Nova](https://github.com/SchweppeLab/Nova) - C# library for reading, writing, and managing MS spectra/data with open standards, aimed at real-time MS app development (pairs with Corona/Helios) ([paper](https://doi.org/10.1021/jasms.5c00141)). `[API]` 🪟
- [mzcore (rustyms)](https://github.com/rusteomics/mzcore) - Rust (and Python) libraries for ProForma peptidoforms, theoretical fragmentation, and spectrum matching across complex PTM/XL/glyco cases; powers Annotator ([paper](https://doi.org/10.1021/acs.analchem.5c02832)). `[API]`
- [Philosopher](https://philosopher.nesvilab.org/) - Toolkit wrapping the Trans-Proteomic Pipeline for validation, inference, FDR filtering, and quantification. `[CLI]`
- [Trans-Proteomic Pipeline (TPP)](http://www.tppms.org/) - Open-source suite covering identification, validation, quantification, and visualization. `[CLI]` `[GUI]`
- [MSnbase](https://bioconductor.org/packages/MSnbase) - R/Bioconductor infrastructure for manipulation, processing, and visualization of MS data. `[API]`
- [R for Mass Spectrometry](https://www.rformassspectrometry.org/) - Coordinated R/Bioconductor ecosystem (Spectra, QFeatures, MsExperiment, PSMatch, PTMods, and more) for interoperable MS proteomics and metabolomics analysis. `[API]`
- [PSMatch](https://bioconductor.org/packages/PSMatch) - R/Bioconductor package to load and filter PSMs, model peptide–protein adjacency/shared peptides, and annotate MS2 fragment ions ([preprint](https://doi.org/10.31219/osf.io/62v9p_v2)). `[API]`
- [ProteoPy](https://github.com/UKHD-NP/proteopy) - AnnData-based Python framework for peptide- and protein-level quantitative proteomics (import, QC, differential testing, COPF proteoform grouping) with scanpy/muon compatibility ([preprint](https://doi.org/10.64898/2026.03.31.715273)). `[API]` 🧪
- [alphapepttools](https://github.com/MannLabs/alphapepttools) - Search- and quantification-engine-agnostic downstream proteomics toolkit that loads results via AlphaBase into AnnData for Scverse/scanpy workflows (v0.2.0; optional AlphaQuant differential expression). `[API]`
- [MS-DAP](https://github.com/ftwkoopmans/msdap) - Downstream analysis pipeline for label-free proteomics that standardizes quality control, normalization, and differential expression across upstream tools such as MaxQuant, DIA-NN, FragPipe, and Spectronaut. `[CLI]` `[API]` 📦
- [Ursgal](https://github.com/ursgal/ursgal) - Python module providing a unified interface to run, combine, and post-process results from multiple bottom-up search engines. `[CLI]` `[API]`
- [ProteomIQon](https://csbiology.github.io/ProteomIQon/) - Modular F# CLI toolkit for building MS proteomics pipelines (signal detection, PSM scoring, protein inference, LFQ/15N quantification) ([Zenodo](https://doi.org/10.5281/zenodo.6335068)). `[CLI]`
- [ProtPipe](https://github.com/NIH-CARD/ProtPipe) - Singularity/CLI pipeline for DIA-NN, Spectronaut, and FragPipe proteomics/peptidomics (QC, DE, enrichment, AP-MS, immunopeptidomics); active R rewrite is [ProtPipe2](https://github.com/NIH-CARD/ProtPipe2) ([paper](https://doi.org/10.1093/gpbjnl/qzae083)). `[CLI]` `[GUI]` 📦

### Cloud & HPC

- [nf-core/quantms](https://github.com/bigbio/quantms) - Cloud-ready Nextflow DDA LFQ/TMT pipeline (and ecosystem at [quantms.org](https://quantms.org/)); DIA moved to [quantmsdiann](https://github.com/bigbio/quantmsdiann); nf-core mirror archived at 1.2.0 ([paper](https://doi.org/10.1038/s41592-024-02343-1)). `[DDA]` `[TMT]` `[Label-Free]` `[CLI]` 📦
- [Frag'n'Flow](https://github.com/ronalabrcns/FragNFlow) - Nextflow pipeline wrapping the FragPipe ecosystem for large-scale quantitative proteomics on HPC, cloud, and clusters, validated across label-free DDA, DIA, and TMT datasets (v2.0.0; [paper](https://doi.org/10.1186/s12859-025-06305-y)). `[DDA]` `[DIA]` `[TMT]` `[Label-Free]` `[CLI]` 📦
- [WOMBAT-P](https://github.com/wombat-p/WOMBAT-Pipelines) - Nextflow platform for running and benchmarking alternative label-free proteomics workflows from SDRF-Proteomics / ProteomeXchange inputs (v0.9.12) ([paper](https://doi.org/10.1021/acs.jproteome.3c00636)). `[Label-Free]` `[CLI]` 📦
- [MoTrPAC proteomics pipeline](https://github.com/MoTrPAC/motrpac-proteomics-pipeline) - WDL/Cromwell cloud pipeline for MoTrPAC MS-GF+ (MASIC/PlexedPiper) and MaxQuant analyses on GCP (v1.3.0; [Zenodo](https://doi.org/10.5281/zenodo.13235298)). `[TMT]` `[CLI]` 📦
- [MS-PyCloud](https://github.com/huizhanglab-jhu/ms-pycloud) - AWS cloud GUI pipeline for proteomic and glycoproteomic LC-MS/MS (search, FDR, protein inference, protein/glyco/PTM quant) ([paper](https://doi.org/10.1021/acs.analchem.3c01497)). `[GUI]` `[CLI]`
- [nf-core/proteomicslfq](https://github.com/nf-core/proteomicslfq) - OpenMS and MSstats label-free quantification pipeline; the predecessor to quantms, now largely superseded (DSL1). `[Label-Free]` `[CLI]` 📦
- [snakemake-ms-proteomics](https://github.com/MPUSP/snakemake-ms-proteomics) - Snakemake pipeline for label-free DDA built on FragPipe and MSstats with automated quality control. `[DDA]` `[Label-Free]` `[CLI]` 📦
- [Galaxy Proteomics (usegalaxy.eu)](https://proteomics.usegalaxy.eu/) - Dedicated European Galaxy proteomics server (Galaxy-P) hosting MS proteomics and proteogenomics tools and workflows that run in the browser without local installation. `[GUI]`
- [Sage](https://github.com/lazear/sage) - See [Identification](#identification). Cloud-ready Rust engine that streams data directly from S3 for large-scale searches.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## AI & Machine Learning in Proteomics

_Last Verified: Q2 2026_

> Machine learning and deep learning applied to proteomics. Entries require a working repository with documentation.

- [Prosit](https://www.proteomicsdb.org/prosit/) - Deep learning models for fragment intensity and retention time prediction, used for spectral libraries and rescoring. `[API]`
- [DeepLC](https://github.com/compomics/DeepLC) - Retention time prediction for peptides, including modified peptides not seen during training. `[CLI]` `[API]`
- [Casanovo](https://github.com/Noble-Lab/casanovo) - Transformer de novo peptide sequencer (and DB-search scoring) from MS/MS spectra; v5.2.0 adds timsTOF .d support ([paper](https://doi.org/10.1038/s41467-024-49731-x)). `[CLI]`
- [Transformer-DIA](https://github.com/Biocomputing-Research-Group/Transformer-DIA) - Transformer de novo peptide sequencer for multiplexed DIA MS/MS spectra ([paper](https://doi.org/10.1109/bibe60311.2023.00013)). `[DIA]` `[CLI]`
- [NovoRank](https://github.com/HanyangBISLab/NovoRank) - Spectral-clustering + deep-learning re-ranker that improves PSM precision/recall for Casanovo, PEAKS, and pNovo3 de novo outputs ([paper](https://doi.org/10.1021/acs.jproteome.4c00300)). `[CLI]`
- [Modanovo](https://github.com/gagneurlab/Modanovo) - PTM-aware de novo sequencer built on Casanovo, trained on in vivo and synthetic modified spectra (MULTI-PTM / PROSPECT-PTM) ([paper](https://doi.org/10.1016/j.mcpro.2025.101501)). `[CLI]`
- [MSBooster](https://github.com/Nesvilab/MSBooster) - Adds deep-learning-predicted features (spectra, retention time) to rescore peptide identifications. `[CLI]`
- [Oktoberfest](https://github.com/wilhelm-lab/oktoberfest) - Open-source Prosit-based pipeline for collision energy calibration, rescoring, and spectral library generation. `[CLI]`
- [MS2PIP](https://github.com/compomics/ms2pip) - Machine-learning predictor of peptide fragmentation spectra for spectral libraries and rescoring. `[CLI]` `[API]`
- [Altimeter](https://github.com/GoldfarbLab/Altimeter) - Transformer that predicts NCE-dependent fragment intensities via cubic B-splines (isolation-window–aware isotopes); hosted on Koina and paired with Pioneer DIA ([preprint](https://doi.org/10.64898/2026.02.16.706201)). `[API]` 🧪
- [MS2Rescore](https://github.com/compomics/ms2rescore) - Modular rescoring framework that adds predicted spectral and related features to boost peptide identifications; TIMS²Rescore mode optimizes DDA-PASEF / timsTOF workflows with IM2Deep ([paper](https://doi.org/10.1021/acs.jproteome.4c00609)). `[CLI]`
- [InstaNovo](https://github.com/instadeepai/InstaNovo) - De novo peptide sequencing combining a transformer model (InstaNovo) with a diffusion model (InstaNovo+) that refines predicted sequences by iterative decoding ([paper](https://doi.org/10.1038/s42256-025-01019-5)). `[CLI]`
- [Pfly](https://github.com/wilhelm-lab/dlomix) - Deep learning peptide detectability (flyer/non-flyer) predictor shipped in the DLOmix framework, fine-tunable per experiment ([paper](https://doi.org/10.1021/acs.jproteome.4c00973)). `[CLI]` `[API]`
- [DeepPD](https://github.com/leonern/DeepPD) - Peptide detectability predictor combining ESM-2 embeddings with an information-bottleneck multi-feature model ([paper](https://doi.org/10.1007/s12539-024-00665-4)). `[CLI]`
- [yHydra](https://gitlab.com/dacs-hpi/yHydra) - Foundation model that jointly embeds MS/MS spectra and peptides for open and error-tolerant searching in embedding space ([preprint](https://doi.org/10.1101/2021.12.01.470818)). `[CLI]` 🧪
- [SpecEncoder](https://github.com/lkytal/SpecEncoder) - Deep metric learning that embeds experimental and predicted MS/MS spectra for spectral-library, database, and hybrid peptide search ([paper](https://doi.org/10.1093/bioinformatics/btae220)). `[CLI]`
- [BiomarkerML](https://github.com/anand-imcm/proteomics-ML-workflow) - Cloud WDL workflow for automated ML/DL biomarker discovery from proteomic matrices (nested CV, SHAP feature ranking, enrichment/PPI follow-up) ([preprint](https://doi.org/10.1101/2025.10.16.682839)). `[CLI]` 📦 🧪
- [ProteoNet](https://github.com/whisperH/ProteoNet) - CNN framework for clinical phenotype classification from proteomics data rendered as MS-RGB images ([paper](https://doi.org/10.1016/j.isci.2024.111362)). `[CLI]`

### Foundation Models / Protein Language Models (pLMs)

> Spectrum prediction (Prosit, Koina), retention time prediction, protein representation learning (ESM, ProtTrans), and AlphaFold integrations applied to MS data.

&#x1F4D6; _Guide:_ [AI/ML in Proteomics](guides/ai-ml-in-proteomics.md) _(planned)_

- [Koina](https://koina.wilhelmlab.org/) - Open service and API network that serves many proteomics ML models (Prosit, AlphaPeptDeep, and more) for prediction and rescoring. `[API]` 📦
- [AlphaPeptDeep](https://github.com/MannLabs/alphapeptdeep) - Deep learning framework for building MS2, retention time, and collision cross section prediction models. `[CLI]` `[API]`
- [ESM (Evolutionary Scale Modeling)](https://github.com/evolutionaryscale/esm) - Protein language models (ESM-2 and ESMFold, plus the newer ESM3 and ESMC) for sequence representation, structure-aware embeddings, and structure prediction; the original facebookresearch/esm repository is now archived. `[API]`
- [ProtSyntax](https://github.com/Yuqiu-rgb/ProtSyntax) - PTM-aware protein language model for site/type prediction, crosstalk, and functional effects across many modification classes ([preprint](https://doi.org/10.64898/2026.07.18.739331)). `[API]` 🧪
- [PTM-Mamba](https://github.com/programmablebio/ptm-mamba) - PTM-aware protein language model with bidirectional gated Mamba blocks fused to ESM-2 embeddings ([paper](https://doi.org/10.1038/s41592-025-02656-9)). `[API]`
- [ProtTrans](https://github.com/agemagician/ProtTrans) - Collection of pretrained protein language models for transfer learning on protein sequences. `[API]`
- [AlphaFold](https://github.com/google-deepmind/alphafold) - Protein structure prediction models, from AlphaFold2 to the newer AlphaFold3 ([source](https://github.com/google-deepmind/alphafold3), released for non-commercial use), increasingly integrated with MS-based proteomics workflows. `[CLI]`
- [ColabFold](https://github.com/sokrypton/ColabFold) - Protein structure prediction that accelerates AlphaFold2 and ESMFold by replacing the MSA step with MMseqs2 search, runnable in Google Colab or on the command line. `[CLI]` `[API]`

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Data Repositories & Standards

_Last Verified: Q2 2026_

> Public repositories, data standards, controlled vocabularies, and format specifications.

&#x1F4D6; _Guides:_ [File Format Cheat Sheet](guides/file-format-cheat-sheet.md) &middot; [Tool Compatibility Matrix](guides/compatibility-matrix.md)

- [CPTAC / Proteomic Data Commons](https://pdc.cancer.gov/) - Repository for harmonized cancer proteogenomic datasets from the CPTAC program.
- [HUPO-PSI Standards](https://www.psidev.info/) - Community data standards and controlled vocabularies (mzML, [mzIdentML 1.3.0](https://www.psidev.info/mzidentml) with crosslinking/multi-spectrum extensions, mzTab, and more) ([mzIdentML 1.3 paper](https://doi.org/10.1002/pmic.202300385)).
- [iProX](https://www.iprox.cn/) - ProteomeXchange member repository in China for raw data, analysis results, and metadata.
- [jPOST](https://jpostdb.org/) - Japan-based ProteomeXchange environment with jPOSTrepo ([repository](https://repository.jpostdb.org/)) for data deposition and jPOSTdb for uniformly reprocessed results.
- [MassIVE](https://massive.ucsd.edu/) - Repository for MS proteomics data with reanalysis and dataset-derived spectral libraries.
- [π-MSNet](https://msnet.ncpsb.org.cn/) - Billion-scale AI-ready proteomics data portal (~1.66B spectra / 501M PSMs) with QPX Parquet access and MSNetLoader for model training and benchmarking ([preprint](https://doi.org/10.64898/2026.04.13.718149)). `[API]` 🧪
- [Panorama Public](https://panoramaweb.org/home/wiki-page.view?name=panorama_public) - ProteomeXchange member repository for Skyline documents and targeted proteomics datasets linked to publications. _See also: [Panorama](#targeted--srm--prm)_
- [ppx](https://github.com/wfondrie/ppx) - Python interface to find and download files and metadata from ProteomeXchange repositories. `[CLI]` `[API]`
- [PRIDE](https://www.ebi.ac.uk/pride/) - Repository for mass spectrometry proteomics data hosted at EMBL-EBI, and a founding member of the ProteomeXchange consortium.
- [ProteomeXchange](https://www.proteomexchange.org/) - Consortium providing a single point of submission and access across major proteomics repositories.
- [ProteoWizard](https://proteowizard.sourceforge.io/) - Cross-platform libraries and tools (including msconvert) for converting and processing raw vendor data. `[CLI]` `[GUI]` 🐧 🪟 🍎
- [PXAudit](https://github.com/LangeLab/PXAudit) - Command-line tool that audits PRIDE dataset metadata, scoring each study on a 7-tier FAIR ladder and a separate quantification-readiness tier and writing results to a local SQLite database. `[CLI]`
- [pxseek](https://github.com/LangeLab/pxseek) - Python command-line tool and library to query, filter, and retrieve dataset metadata from ProteomeXchange through its fetch, filter, and lookup commands, writing reusable summary tables for reproducible dataset shortlisting. `[CLI]` `[API]`
- [ThermoRawFileParser](https://github.com/compomics/ThermoRawFileParser) - Cross-platform converter from Thermo raw files to open formats such as mzML and MGF. `[CLI]` 🐧 🪟 🍎
- [usiGrabber](https://github.com/usiGrabber/usiGrabber) - Scalable framework that parses PRIDE mzIdentML into a USI-indexed database and downloads/export spectra for ML-ready proteomics datasets ([preprint](https://doi.org/10.64898/2026.03.15.711873)). `[CLI]` `[API]` 🧪

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Protein Databases & Knowledge Bases

_Last Verified: Q2 2026_

> Protein sequence, structure, family, function, enzyme, pathway, interaction, disease, and proteoform databases. Includes general biological knowledge bases beyond proteomics that are widely used in proteomics research. For data submission and reanalysis repositories see [Data Repositories & Standards](#data-repositories--standards).

### Sequence & Function Knowledge Bases

- [APPRIS](https://appris.bioinfo.cnio.es/) - Selects principal protein isoforms per gene using structure, function, and conservation evidence, useful when building non-redundant proteomics search databases.
- [Ensembl](https://www.ensembl.org/) - Integrates genome annotation across vertebrate and other eukaryotic species, providing gene, transcript, and protein sequences with cross-references used to map proteomics identifiers.
- [GeneCards](https://www.genecards.org/) - Aggregates gene-centric genomic, transcriptomic, proteomic, and disease information for human genes from many integrated sources.
- [HGNC](https://www.genenames.org/) - Assigns approved, unique symbols and names for human genes and their protein products to provide stable identifiers for cross-referencing.
- [NCBI RefSeq](https://www.ncbi.nlm.nih.gov/refseq/) - Provides a curated, non-redundant collection of reference genomic, transcript, and protein sequences used for annotation and as proteomics search databases.
- [neXtProt](https://www.expasy.org/archives/nextprot) - Integrates human protein sequence, expression, interaction, PTM, and variant data; reached end of life in 2024 after 14 years, with its data and tools archived on Expasy and still downloadable.
- [Proteome Quality Index (PQI)](https://pqi-list.org/) - Rates downloadable organism proteomes with a multi-metric 1–5 star score to help choose higher-quality FASTA search databases.
- [UniParc](https://www.uniprot.org/uniparc) - Maintains a non-redundant archive of protein sequences from public databases, retaining sequences removed from UniProtKB.
- [UniProt](https://www.uniprot.org/) - Provides protein sequences and functional annotation through the manually reviewed Swiss-Prot and automatically annotated TrEMBL sections of UniProtKB.
- [UniProt Proteomes](https://www.uniprot.org/proteomes) - Provides per-organism protein sets for species with sequenced genomes, used as reference search databases in proteomics (human reference proteome UP000005640).
- [UniRef](https://www.uniprot.org/uniref) - Provides clustered sequence sets (UniRef100, UniRef90, UniRef50) that reduce redundancy for faster similarity searches and profile building.

> Note: Starting with release 2025_04 (October 2025) and completing with release 2026_02 (mid-2026), UniProtKB is being reduced to proteins from reference proteomes, plus reviewed Swiss-Prot entries and entries of high biological relevance; removed sequences remain searchable and downloadable in UniParc.

### Structure Databases

- [AlphaFold Protein Structure Database](https://alphafold.ebi.ac.uk/) - Provides over 214 million predicted protein structures from AlphaFold, developed by Google DeepMind and EMBL-EBI under a CC-BY-4.0 licence.
- [CATH](https://www.cathdb.info/) - Classifies protein domain structures from the PDB into a hierarchy of class, architecture, topology, and homologous superfamily.
- [DisProt](https://disprot.org/) - Curates experimentally validated intrinsically disordered proteins and regions with manual structural and functional annotations from the literature.
- [EncoMPASS](https://encompass.ninds.nih.gov/) - Relates integral membrane protein PDB structures by sequence, fold, and quaternary/internal symmetry relative to the membrane (v2.1.2; updated 2025).
- [MobiDB](https://mobidb.org/) - Annotates intrinsically disordered proteins and regions by combining curated annotations, indirect structural evidence, and sequence-based predictions.
- [PDBe (Protein Data Bank in Europe)](https://www.ebi.ac.uk/pdbe/) - Provides the European wwPDB access point for macromolecular structures with search, analysis, and Mol\* visualization services.
- [RCSB Protein Data Bank (PDB)](https://www.rcsb.org/) - Provides the US access point to experimentally determined 3D structures of proteins, nucleic acids, and complexes archived by the wwPDB.
- [SCOP](https://www.ebi.ac.uk/pdbe/scop/) - Classifies protein domains of known structure into families, superfamilies, and folds based on structural and evolutionary relationships.
- [wwPDB](https://www.wwpdb.org/) - Consortium that manages the single global Protein Data Bank archive and OneDep deposition system across RCSB PDB, PDBe, PDBj, BMRB, and EMDB.

### Families, Domains & Ontologies

- [ELM (Eukaryotic Linear Motif resource)](http://elm.eu.org/) - Annotates and predicts short linear motifs that mediate protein interactions and regulation in eukaryotic proteins.
- [Gene Ontology (GO)](https://geneontology.org/) - Provides a controlled vocabulary and annotations describing protein molecular functions, biological processes, and cellular components.
- [InterPro](https://www.ebi.ac.uk/interpro/) - Classifies proteins into families and predicts domains and functional sites by integrating signatures from multiple member databases.
- [InterProScan 6](https://github.com/ebi-pf-team/interproscan6) - Nextflow pipeline for genome-scale InterPro member-database annotation with containerized runs and a Matches API for pre-computed results (successor to InterProScan 5). `[CLI]` 📦
- [PANTHER](https://www.pantherdb.org/) - Classifies proteins by family, subfamily, molecular function, biological process, and pathway using phylogenetic trees.
- [Pfam](https://www.ebi.ac.uk/interpro/entry/pfam/) - Provides protein families represented by multiple sequence alignments and hidden Markov models, now hosted within InterPro.
- [PROSITE](https://prosite.expasy.org/) - Documents protein domains, families, and functional sites with patterns and profiles, complemented by ProRule annotation rules.
- [SMART](https://smart.embl.de/) - Identifies and annotates protein domains and analyzes domain architectures using manually curated domain models.
- [SUPERFAMILY](https://supfam.org/) - Annotates protein domains at the SCOP superfamily level with HMM libraries across sequenced genomes; also contributed as an InterPro member database.

### Enzymes & Peptidases

- [BRENDA](https://www.brenda-enzymes.org/) - Provides functional enzyme data including kinetics, substrates, reactions, and organisms organized by EC classification; free under a CC-BY-4.0 licence.
- [CAZy](https://www.cazy.org/) - Classifies carbohydrate-active enzymes into sequence-based families that link sequence to structure, mechanism, and specificity.
- [MEROPS](https://www.ebi.ac.uk/merops/) - Classifies peptidases (proteases), their inhibitors, and substrates into a structure-based hierarchy of families and clans.
- [TopFIND](https://topfind.clip.msl.ubc.ca/) - Knowledge base of protein termini, their generation by proteases, and the functional implications, integrating curated and community-contributed cleavage and processing data with the TopFINDer and PathFINDer analysis tools.
- [CLIPPER 2.0](https://github.com/UadKLab/CLIPPER-2.0) - Peptide-level annotation and analysis for positional proteomics / degradomics (termini, neo-termini, protease substrates) from Proteome Discoverer, Spectronaut, or FragPipe ([paper](https://doi.org/10.1016/j.mcpro.2024.100781)). `[CLI]` `[API]`

### Pathways & Interactions

- [BioGRID](https://thebiogrid.org/) - Curates protein, genetic, and chemical interactions and post-translational modifications from published literature.
- [Complex Portal](https://www.ebi.ac.uk/complexportal) - Provides manually curated macromolecular complexes for key model organisms, supplemented by machine-learning-predicted human complexes.
- [CORUM](https://mips.helmholtz-muenchen.de/corum/) - Provides manually curated, experimentally characterized mammalian protein complexes with composition, function, and localization.
- [GeneMANIA](https://genemania.org/) - Predicts gene and protein function by integrating association networks from co-expression, interaction, and pathway data.
- [hu.MAP 3.0](https://humap3.proteincomplexes.org/) - Atlas of >15,000 human protein complexes from machine-learning integration of >25,000 mass spectrometry experiments, also deposited in the Complex Portal.
- [IntAct](https://www.ebi.ac.uk/intact/) - Provides molecular interactions from literature curation and direct submissions, and produces the Complex Portal.
- [KEGG](https://www.genome.jp/kegg/) - Provides manually drawn pathway maps linking genes and proteins to metabolism, signaling, and disease; web access is free for academic use while bulk downloads require a license.
- [MINT](https://mint.bio.uniroma2.it/) - Stores experimentally verified protein-protein interactions curated from the literature, integrated with IntAct under the IMEx consortium.
- [Pathway Commons](https://www.pathwaycommons.org/) - Aggregates pathway and molecular interaction data from many source databases into a single resource queryable in BioPAX format.
- [Reactome](https://reactome.org/) - Provides curated, peer-reviewed biological pathways with tools for visualization and enrichment analysis.
- [SIGNOR](https://signor.uniroma2.it/) - Stores manually curated causal signaling interactions, including phosphorylation events, as customizable directional networks.
- [STRING](https://string-db.org/) - Known and predicted protein associations (functional, physical, and regulatory/directional networks in v12.5) with enrichment and clustering ([paper](https://doi.org/10.1093/nar/gkae1113)).
- [WikiPathways](https://www.wikipathways.org/) - Provides an open, community-curated collection of biological pathways available for download and enrichment analysis.

### Disease, Drug & Target Knowledge Bases

- [ChEMBL](https://www.ebi.ac.uk/chembl/) - Provides manually curated bioactivity data linking drug-like molecules to protein targets under a CC-BY-SA licence.
- [DBSAV](http://prodata.swmed.edu/DBSAV/) - Reports DeepSAV deleteriousness scores for human single-amino-acid variants and gene-level GTS tolerance scores with sequence and structure context.
- [ProteoCast](https://github.com/abakarovaMarina/ProteoCast) - GEMME-based proteome-wide missense variant effect predictor that classifies substitutions as neutral, mild, or impactful and flags mutation-sensitive sites ([paper](https://doi.org/10.1038/s41467-026-72140-1)). `[CLI]`
- [DisGeNET](https://www.disgenet.com/) - Integrates gene-disease and variant-disease associations from curated databases and text mining; now distributed under a freemium model requiring registration. 💰
- [DrugBank](https://go.drugbank.com/) - Provides drug, drug-target, mechanism, and interaction data; free for academic use under license with commercial tiers. 💰
- [OMIM](https://www.omim.org/) - Catalogs human genes and genetic disorders with curated gene-to-phenotype relationships from the biomedical literature.
- [Open Targets Platform](https://platform.opentargets.org/) - Integrates genetic, omics, and literature evidence to score and prioritize therapeutic targets for diseases.
- [Pharos](https://pharos.nih.gov/) - Presents target, disease, and ligand data from the Illuminating the Druggable Genome program with emphasis on understudied human proteins.
- [PMADS](https://pmads.org/) - Database of curated and proteomics-inferred PTM–drug–disease associations linking modification sites to drug sensitivity contexts ([paper](https://doi.org/10.1093/nar/gkaf1033)).
- [decryptM](https://www.proteomicsdb.org/decryptM) - ProteomicsDB resource of dose- and time-resolved MS PTM responses to cancer drugs (~1.8M curves; phospho/ub/acetyl) with analysis pipeline ([paper](https://doi.org/10.1126/science.ade3925)). `[GUI]`
- [PTMD 2.0](http://ptmd.biocuckoo.cn/) - Manually curated database of disease-associated PTMs (~343k associations across 93 PTM types and ~2k diseases) with multi-resource protein annotations ([paper](https://doi.org/10.1093/nar/gkae850)).
- [Unknome](https://unknome.mrc-lmb.cam.ac.uk/) - Ranks protein families by how little is known about them using weighted Gene Ontology evidence (v3; updated March 2026), helping prioritize understudied conserved proteins.

### Expression & Proteoform Atlases

- [Blood Proteoform Atlas](https://blood-proteoform-atlas.org/) - Provides a reference map of proteoforms across human hematopoietic cell types in blood and bone marrow.
- [Expression Atlas](https://www.ebi.ac.uk/gxa/home) - Provides gene and protein expression results across tissues, cell types, and conditions from curated RNA-seq and proteomics studies.
- [GPMDB](https://gpmdb.thegpm.org/) - Global Proteome Machine Database of observed peptide and protein evidence from public tandem MS data reanalyzed with X!Tandem; US IP addresses have been blocked from queries since February 2025.
- [GTEx Portal](https://gtexportal.org/home/) - Provides tissue-specific gene expression and regulatory data across human tissues from a large donor cohort.
- [Human Protein Atlas](https://www.proteinatlas.org/) - Maps human protein expression and subcellular localization across tissues, cells, organs, and blood using imaging, mass spectrometry, and transcriptomics.
- [Human Proteoform Atlas](https://human-proteoform-atlas.org/) - Provides experimentally verified human proteoforms, descended from the Consortium for Top-Down Proteomics Proteoform Atlas.
- [Human Proteome Map](http://www.humanproteomemap.org/) - Provides a draft map of human protein expression across adult and fetal tissues from the Kim et al. proteome study.
- [PeptideAtlas](https://peptideatlas.org/) - Provides a multi-organism compendium of peptides identified across uniformly reprocessed tandem MS datasets.
- [E. coli PeptideAtlas](https://peptideatlas.org/builds/ecoli/) - Pan-proteome PeptideAtlas build from ~73M spectra across 40 E. coli datasets (closed + open search), including >10k PTM sites ([paper](https://doi.org/10.1021/acs.jproteome.5c00902)).
- [Borrelia PeptideAtlas](https://peptideatlas.org/builds/borrelia/) - Uniformly reprocessed B. burgdorferi PeptideAtlas build (2024-03) across isolates B31, MM1, and B31-5A4 (~82k peptides; PRIDE PXD046281) ([paper](https://doi.org/10.1038/s41597-024-04047-9)).
- [PanNDA](https://penglab.shinyapps.io/pannda/) - Interactive pan-neurodegeneration proteomics atlas from ~2,279 human brain samples across six diseases, spanning whole/insoluble proteomes plus phospho- and ubiquitinomes ([paper](https://doi.org/10.1016/j.cell.2026.02.026)). `[GUI]`
- [BrainProt](https://www.brainprot.org/) - Omics knowledge base for human brain diseases with proteome/phosphoproteome maps (BDPM, IBPM), marker curation, and drug/clinical-trial browsing ([paper](https://doi.org/10.1021/acs.jproteome.4c00982)).
- [Human Blood Proteomics Atlas (HuBP)](https://protein-notebook.streamlit.app/) - Streamlit atlas of MS blood/plasma protein detectability, intensity, and reproducibility across sample-prep methods (~12k proteins) ([preprint](https://doi.org/10.1101/2025.05.15.654311)). `[GUI]` 🧪
- [Proteoform Atlas (CTDP)](https://atlas.topdownproteomics.org/) - Consortium for Top-Down Proteomics repository of experimentally observed proteoforms across organisms and datasets; the human-focused FAIR descendant is the Human Proteoform Atlas.
- [ProteinExplorer](https://massive.ucsd.edu/ProteoSAFe/protein_explorer_splash.jsp) - Interactive MassIVE viewer mapping MassIVE-KB reanalysis evidence onto human proteins with coverage maps, functional sites, and spectrum provenance.
- [ProteomicsDB](https://www.proteomicsdb.org/) - Provides a knowledge base of protein expression and related multi-omics measurements, and hosts the Prosit prediction service.
- [QCPA (Quantitative Cell Proteomic Atlas)](https://qcpa.mskcc.org/) - Pathway-scale targeted MS assay panels for abundance and PTM stoichiometry of human cell-signaling effectors (~1,900 peptides; includes TrypQuant digestion controls). `[Targeted]`
- [SRMAtlas](https://srmatlas.org/) - Provides targeted SRM/MRM assays built from synthetic peptides to detect and quantify proteins across complete proteomes.
- [ShinySperm](https://reproproteomics.shinyapps.io/ShinySperm/) - Interactive atlas of epididymal sperm MS proteomes (domains, maturation stages, classifications); multi-species companion is [ShinySpermKingdom](https://reproproteomics.shinyapps.io/ShinySpermKingdom/) ([paper](https://doi.org/10.1071/rd24079)). `[GUI]`
- [SubCellBarCode](https://data.scilifelab.se/services/subcellbarcode/) - MS fractionation resource and workflow mapping subcellular localization for ~12,400 genes across five cell lines, with a Bioconductor analysis package. `[API]`
- [REMEMProt](https://rememprot.ciods.in/) - Curated human and mouse membrane-enriched MS proteome profiles (~14.6k proteins) with enrichment-method context, disease associations, and biomarker status ([paper](https://doi.org/10.26508/lsa.202302443)).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Multi-Omics Integration

_Last Verified: Q2 2026_

> Tools for integrating proteomics with genomics, transcriptomics, and metabolomics. Focus on proteomics-centric or proteomics-aware integrations.

- [MOFA+ / MOFA2](https://biofam.github.io/MOFA2/) - Unsupervised factor-analysis framework that integrates multiple omics layers into shared, interpretable latent factors. `[CLI]` `[API]`
- [mixOmics](https://mixomics.org/) - R package of multivariate methods for omics exploration and integration, including the DIABLO supervised multi-omics framework. `[CLI]`
- [WGCNA](https://cran.r-project.org/package=WGCNA) - R package for weighted correlation network analysis that finds co-expression modules and relates them to sample traits. `[CLI]`
- [COSMOS](https://saezlab.github.io/cosmosR/) - Integrates phosphoproteomics, transcriptomics, and metabolomics with prior-knowledge networks to infer causal mechanistic hypotheses. `[CLI]`
- [OmicsAnalyst](https://www.omicsanalyst.ca/) - Web platform for statistical, visual, and network-based integration of multiple omics datasets.
- [LinkedOmics](https://www.linkedomics.org/) - Web portal to access and correlate multi-omics data, including CPTAC proteomics, across TCGA and CPTAC cancer cohorts.
- [cProSite](https://cprosite.ccr.cancer.gov) - Interactive CPTAC cancer proteogenomics browser for tumor/normal protein, phosphosite, and mRNA comparisons and correlations ([paper](https://doi.org/10.26502/jbb.2642-91280119)). `[GUI]`
- [muon](https://muon.scverse.org/) - Python framework built on the MuData structure for multimodal single-cell and multi-omics analysis. `[API]`
- [mogsa](https://bioconductor.org/packages/mogsa) - R/Bioconductor package for multi-omics integrative clustering (moCluster) and single-sample multi-omics gene set analysis. `[CLI]`
- [PEARL](https://github.com/zqq121017/PEARL) - Supervised deep graph learning for multi-omics classification and feature discovery that builds Pearson sample-similarity networks and spectral GCNs (benchmarks include protein abundance layers) ([paper](https://doi.org/10.1093/bioinformatics/btag253)). `[CLI]`
- [AART](https://github.com/saizhanglab/AART) - Cross-platform plasma proteomics translator that imputes between mass spectrometry, Olink, and SomaScan using anchor-aware residual models ([preprint](https://doi.org/10.64898/2026.06.29.735313)). `[CLI]` `[API]` 🧪
- [DancePartner](https://github.com/pnnl-predictive-phenomics/DancePartner) - Python package that mines multi-omics biomolecule relationship networks from literature and databases (KEGG, WikiPathways, UniProt, LipidMaps) ([paper](https://doi.org/10.1021/acs.jproteome.5c00520)). `[CLI]` `[API]`
- [Flexynesis](https://github.com/BIMSBbioinfo/flexynesis) - Deep learning toolkit for bulk multi-omics integration (including proteomics) with HPO, multi-task prediction, and Captum marker ranking; Galaxy/Bioconda deployable ([paper](https://doi.org/10.1038/s41467-025-63688-5)). `[CLI]` `[API]` 📦
- [ProteinProjector](https://github.com/idekerlab/cellmaps_coembedding) - Self-supervised Cell Mapping Toolkit co-embedding that unifies AP-MS, proximity-labeling MS, SEC-MS, and imaging into protein-position maps ([paper](https://doi.org/10.1093/bioadv/vbaf266)). `[CLI]` `[API]`
- [Profiler](https://prism-profiler.univ-lille.fr/) - Open web/desktop multi-omics analysis platform with native MaxQuant, DIA-NN, Spectronaut, and FragPipe proteomics import, QC, DE, ML, and enrichment ([paper](https://doi.org/10.1093/bioinformatics/btaf644)). `[GUI]`

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Frontier & Niche Techniques

_Last Verified: Q2 2026_

> Emerging and specialized proteomics approaches. Honest about sparsity; entries grow as fields mature.

### Metaproteomics

- [Unipept](https://unipept.ugent.be/) - Web application, API, and CLI for taxonomic and functional analysis of metaproteomics peptides; v6.0 adds fast missed-cleavage / semi- and non-tryptic matching ([paper](https://doi.org/10.1021/acs.jproteome.4c00848)). `[GUI]` `[CLI]` `[API]`
- [Peptonizer2000](https://github.com/compomics/Peptonizer2000) - Graphical-model taxonomic inference for metaproteomics that combines search-engine peptide scores with Unipept peptide–taxon maps and reports confidence scores ([paper](https://doi.org/10.1021/acs.jproteome.5c00567)). `[CLI]`
- [MetaLab](https://imetalab.ca/) - Automated platform for metaproteomic identification, quantification, and taxonomic and functional annotation, supporting DDA and DIA data. `[GUI]` 🪟
- [MetaProteomeAnalyzer (MPA)](https://github.com/compomics/meta-proteome-analyzer) - Open-source tool that identifies metaproteomics data and groups results into taxonomic and functional meta-proteins. `[GUI]` `[CLI]`
- [ProteoDUDes](https://github.com/pirovc/dudes) - Taxonomic profiling for metaproteomics that extends DUDes with false-positive reduction over Unipept/DIAMOND-style annotations ([preprint](https://doi.org/10.64898/2026.06.29.734936)). `[CLI]` 🧪
- [MetaUmbra](https://github.com/byemaxx/MetaUmbra) - Genome-level presence inference from metaproteomic peptide lists that combines unique and shared peptide evidence into p/q-values for candidate genomes or MAGs ([preprint](https://doi.org/10.64898/2026.04.29.721689)). `[CLI]` `[GUI]` 🧪
- [NovoTax](https://github.com/mateuslab-prot/NovoTax) - Nextflow pipeline that identifies prokaryotic strains from raw MS proteomics via de novo sequencing and GTDB search, then builds a sample-specific protein FASTA ([preprint](https://doi.org/10.64898/2026.04.02.715787)). `[CLI]` 📦 🧪
- [MegaPX](https://github.com/rki-mf2/MegaPX) - Fast IBF multi-index tool that assigns de novo peptide sequences to large protein databases for metaproteomic taxonomic screening ([paper](https://doi.org/10.1093/bioinformatics/btag134)). `[CLI]`
- [NovoLign](https://github.com/hbckleikamp/NovoLign) - DIAMOND alignment of de novo sequenced peptides for metaproteomic taxonomic profiling, database-search QC, and reference-DB construction ([paper](https://doi.org/10.1093/ismeco/ycae121)). `[CLI]`

### Proteogenomics

- [CHESS 3](https://ccb.jhu.edu/chess/) - Comprehensive human gene and transcript catalog with downloadable protein FASTA sequences for proteogenomics search databases, built from large-scale GTEx RNA-seq.
- [customProDB](https://bioconductor.org/packages/customProDB) - R/Bioconductor package that builds customized protein databases from RNA-seq data for proteomics search. `[CLI]`
- [Brownotate](https://github.com/LSMBO/Brownotate) - Pipeline and web app to assemble/annotate genomes (or fetch existing sequences) into protein FASTA search databases for any species with sequencing data ([paper](https://doi.org/10.1002/pmic.70094)). `[CLI]` `[GUI]` 📦
- [Galaxy-P](https://galaxyp.org/) - Galaxy-based multi-omics platform with workflows for building custom sequence databases and performing proteogenomic analysis. `[GUI]`
- [IsoPepTracker](https://www.isopeptracker.org/) - Web app that maps alternative-splicing / isoform differences to shotgun-detectable peptides for proteogenomic validation and protease selection. `[GUI]`
- [iMPI](https://impi.omicsbio.info/) - Database of intron-retention microproteins in human tumors with large-scale proteomic MS validation across 27 cancer types ([paper](https://doi.org/10.1002/pmic.70142)).
- [PEXMap](https://github.com/deepanshicbg/PEXMap) - Exon-aware proteogenomic mapper that assigns MS/MS peptides to genes, transcripts, exons, and exon–exon junctions via 8-mer dictionaries ([preprint](https://doi.org/10.64898/2026.04.29.721330)). `[CLI]` 🧪
- [ProteoDisco](https://bioconductor.org/packages/ProteoDisco) - R/Bioconductor package for building custom protein-variant databases from genomic variants, splice junctions, fusion genes, and manual transcript sequences for proteogenomic search ([paper](https://doi.org/10.1093/bioinformatics/btab809)). `[API]`
- [ProHap](https://github.com/ProGenNo/ProHap) - Builds haplotype-aware protein search databases from phased genotype panels (1KG/HRC/HPRC), with companion peptide annotator and prebuilt Zenodo FASTAs ([paper](https://doi.org/10.1038/s41592-024-02506-0)). `[CLI]`
- [moPepGen](https://github.com/uclahs-cds/package-moPepGen) - Graph-based generator of non-canonical peptides from genomic/transcriptomic variants (SNV/indel, fusion, splicing, circRNA, RNA editing) for proteogenomic search databases ([paper](https://doi.org/10.1038/s41587-025-02701-0)). `[CLI]`
- [PepCentric](https://peptidecentric.org/) - Web portal for peptide-centric searches of novel sequences against repository-scale indexed MS/MS spectra (~2.3B) for proteogenomic validation ([preprint](https://doi.org/10.1101/2025.02.24.639867)). `[GUI]` 🧪
- [ChiMSource](https://github.com/umutcakir/chimsource) - Finds alternative genomic sources for MS chimeric and non-chimeric peptides via multi-frame translation (successor to ShiftSCAN; frameshifting / mosaic translation studies) ([preprint](https://doi.org/10.1101/2025.05.30.656965)). `[CLI]` 🧪
- [SmProt](http://bigdata.ibp.ac.cn/SmProt/) - Curates small proteins (<100 aa) and sORF products from Ribo-seq, literature, and MS across eight species, useful for microprotein / non-canonical search databases.
- [FuncPEP v2.0](https://bioinformatics.mdanderson.org/Supplements/FuncPEP/) - Curated database of experimentally validated functional short peptides (ncPEPs) translated from non-coding RNAs (~152 entries) ([paper](https://doi.org/10.3390/ncrna10020020)).
- [Spritz](https://smith-chem-wisc.github.io/Spritz/) - Software that builds sample-specific proteoform databases annotated with sequence variants and PTMs from RNA-seq data. `[GUI]` 🪟

### Other Emerging Approaches

> Immunopeptidomics and interaction (AP-MS) proteomics.

- [MHCquant](https://nf-co.re/mhcquant/) - Nextflow/nf-core pipeline for identifying and quantifying MHC-presented (immunopeptidomics) peptides, built on OpenMS. `[CLI]` 📦
- [Immunolyser 2.0](https://immunolyser.erc.monash.edu/) - Web/Docker pipeline for immunopeptidomics peptide-centric analysis (length, motifs, clustering, MHC binding; murine support and MHC-TP haplotype prediction) ([paper](https://doi.org/10.1016/j.csbj.2025.10.007)). `[GUI]` 📦
- [PAMPA](https://github.com/touzet/pampa) - ZooMS/paleoproteomics suite for taxonomic identification from MALDI peptide mass fingerprints using collagen marker tables ([paper](https://doi.org/10.1021/acs.jproteome.5c00389)). `[CLI]` `[GUI]`
- [SAINTexpress](https://saint-apms.sourceforge.net/) - Tool that assigns confidence scores to protein-protein interactions from affinity purification-mass spectrometry (AP-MS) data. `[CLI]`
- [WeSA](https://github.com/russelllab/wesa) - Weighted SocioAffinity scoring/ranking for affinity proteomics bait–prey lists (AP-MS, IP, proximity labeling) with interactive network filtering ([paper](https://doi.org/10.1093/nar/gkae423)). `[GUI]` `[CLI]`
- [MAGPIE](https://github.com/LavalleeAdamLab/MAGPIE) - Logistic-regression confidence scoring for PPIs from human plasma IP-MS/MS using non-plasma antibody negative controls ([paper](https://doi.org/10.1021/acs.jproteome.4c00160)). `[CLI]`
- [CRAPome / RePRINT](https://reprint-apms.org/) - Contaminant repository of negative-control AP-MS data used to estimate background and filter interaction candidates.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Deprecated & Legacy

> Tools and resources that have been superseded by newer versions, archived, or are no longer actively maintained. Kept as a stable home for migration notes and successor pointers; entries are added when the list goes public.

- [neXtProt peptide uniqueness checker](https://www.expasy.org/archives/nextprot) - Web tool for unique/SAAV-aware peptide mapping ended with neXtProt (2024); offline CLI successor [pepx](https://github.com/calipho-sib/pepx) (Schaeffer et al., 2017) remains available. `[CLI]`

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

---

## Community & Organizations

_Last Verified: Q2 2026_

> Professional societies, community channels, conferences, and organizations.

- [ASMS (American Society for Mass Spectrometry)](https://www.asms.org/) - Mass spectrometry society, publisher of the Journal of the American Society for Mass Spectrometry (JASMS) and host of the annual ASMS Conference.
- [Biostars](https://www.biostars.org/) - Question-and-answer forum for bioinformatics, with an active community discussing proteomics data analysis.
- [C-HPP (Chromosome-centric Human Proteome Project)](https://hupo.org/chpp/) - HUPO Human Proteome Project initiative organizing chromosome teams to complete high-stringency detection and functional annotation of the human proteome.
- [EuBIC-MS](https://eubic-ms.org/) - European Bioinformatics Community for Mass Spectrometry, running winter schools, developers meetings, and hackathons.
- [EuPA (European Proteomics Association)](https://eupa.org/) - Federation of 23 European national proteomics societies supporting research, education, and training.
- [HUPO (Human Proteome Organization)](https://hupo.org/) - International organization coordinating global proteomics, the Human Proteome Project, and the annual HUPO World Congress.
- [r/bioinformatics](https://www.reddit.com/r/bioinformatics/) - Reddit community for bioinformatics and computational biology, broader than the proteomics-specific subreddits and frequently covering proteomics data analysis.
- [r/massspectrometry](https://www.reddit.com/r/massspectrometry/) - Reddit community for mass spectrometry discussion spanning proteomics, metabolomics, and instrumentation.
- [r/proteomics](https://www.reddit.com/r/proteomics/) - Reddit community for questions and discussion on proteomics methods, tools, and literature.
- [US HUPO](https://us-hupo.org/) - US national proteomics society with an annual conference and early-career researcher programs.

> See also the [Consortium for Top-Down Proteomics](#top-down-proteomics), listed under Top-Down Proteomics.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

---

## Guides & Workflows

This repository has two companion directories for content that goes beyond a link list:

| Directory    | What it contains                                                                              | Browse                      |
| ------------ | --------------------------------------------------------------------------------------------- | --------------------------- |
| `guides/`    | Opinionated expert deep-dives, decision trees, comparison tables, and mini-guides (500 words) | [All Guides](guides/)       |
| `workflows/` | Practitioner start-to-finish pipelines with Nextflow/Snakemake snippets                       | [All Workflows](workflows/) |

**Published guides:** [Beginner's Guide](guides/beginners-guide.md) &middot; [File Format Cheat Sheet](guides/file-format-cheat-sheet.md) &middot; [Tool Compatibility Matrix](guides/compatibility-matrix.md)

**Planned guides:** [Starter Packs](guides/starter-packs.md) &middot; [DIA Tools Comparison](guides/dia-tools-comparison.md)

**Published workflows:** [Label-Free DDA](workflows/label-free-dda.md)

**Planned workflows:** [DIA Analysis](workflows/dia-analysis.md) &middot; [Phosphoproteomics](workflows/phosphoproteomics.md) &middot; [Single-Cell](workflows/single-cell.md)

Want to write a guide? See the [guide authorship track](CONTRIBUTING.md#guide-and-workflow-authorship) in CONTRIBUTING.md.

---

## Contributing

Contributions are welcome. Please read the [contribution guidelines](CONTRIBUTING.md) first.

Three tracks: **list entries** (tools, resources), **guides** (opinionated deep-dives), and **mini-guides** (500-word focused comparisons).

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, [Zenteomics](https://github.com/zenteomics) has waived all copyright and related or neighboring rights to this work.

---

<p align="center">
  Maintained by <a href="https://github.com/zenteomics">Zenteomics</a><br>
  <sub>Quality over quantity. Judgment over aggregation. Honesty over completeness.</sub>
</p>

<p align="center">
  <a href="CONTRIBUTING.md">Contributing</a> ·
  <a href="GOVERNANCE.md">Governance</a> ·
  <a href="CODE_OF_CONDUCT.md">Code of Conduct</a> ·
  <a href="LICENSE">License</a>
</p>
