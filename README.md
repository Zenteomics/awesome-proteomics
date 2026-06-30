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

*Inclusion does not constitute endorsement. Commercial tools are marked with 💰. See the [contribution guidelines](CONTRIBUTING.md) for entry format and quality bar.*

**Scope:** Mass spectrometry-based proteomics, spanning both bottom-up / shotgun and top-down / native approaches. Affinity- and aptamer-based platforms (for example Olink and SomaScan) are currently out of scope; this list deliberately stays MS-focused.

---

## Recently Added

<!-- Living changelog. Format: YYYY-MM-DD: [Tool Name](url) - One-line description. -->

*No entries yet. This list is being seeded. [Contributions welcome!](CONTRIBUTING.md)*

---

## Contents

- [Recently Added](#recently-added)
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
- [Community \& Organizations](#community--organizations)
- [Deprecated / Legacy](#deprecated--legacy)
- [Guides \& Workflows](#guides--workflows)
- [Contributing](#contributing)
- [License](#license)

---

## Legend

Each entry follows the format `[Name](link) - One-line description.` with optional tags so you can tell, at a glance, how to run a tool and what it does.

**Interface** - how you use it:

| Tag | Meaning |
| ----- | --- |
| `[CLI]` | Runs from the command line (terminal tool or script) |
| `[GUI]` | Graphical desktop or web application |
| `[API]` | Importable library or package you call from code (Python, R, and similar) |

**Data type / workflow** - what it processes:

| Tag | Meaning |
| ----- | --- |
| `[DDA]` | Data-dependent acquisition |
| `[DIA]` | Data-independent acquisition (includes SWATH) |
| `[Label-Free]` | Label-free quantification |
| `[TMT]` | Isobaric labeling (TMT / iTRAQ) |
| `[SILAC]` | Metabolic labeling (SILAC) |
| `[Targeted]` | Targeted assays (SRM / PRM) |

**Status** - maturity and licensing:

| Emoji | Meaning |
| ----- | --- |
| 💰 | Commercial or paid license (a free academic tier may exist) |
| 📦 | Containerized image available (Docker / Singularity) |
| 🏭 | Production-grade / built for high throughput |
| 🧪 | Experimental / research-stage |

**Platform** - shown only when support is non-obvious or restricted:

| Emoji | Meaning |
| ----- | --- |
| 🐧 | Linux |
| 🪟 | Windows |
| 🍎 | macOS |

Tags stack: a single entry can read `[DIA]` `[CLI]` 🐧 🪟. No platform emoji means the tool is broadly cross-platform or runs in the browser.

---

## General Resources

*Last Verified: Q2 2026*

> Start-here guides, courses, books, key reviews, milestone papers, and community media. Includes clinical and medical proteomics resources until that subfield warrants its own section.

### Start Here: Tutorials & Practical Guides

- [A beginner's guide to mass spectrometry-based proteomics](https://portlandpress.com/biochemist/article/42/5/64/226371/A-beginner-s-guide-to-mass-spectrometry-based) - Open-access introduction by Sinha and Mann (2020, The Biochemist) to mass spectrometer components, sample preparation, and quantification strategies.
- [An Introduction to Mass Spectrometry-Based Proteomics](https://doi.org/10.1021/acs.jproteome.2c00838) - Illustrated tutorial by Shuken (2023, Journal of Proteome Research) covering a label-free quantitative experiment from sample preparation to protein-group analysis.
- [Comprehensive Overview of Bottom-Up Proteomics Using Mass Spectrometry](https://doi.org/10.1021/acsmeasuresciau.3c00068) - Crowd-sourced handbook by Jiang, Meyer, et al. (2024, ACS Measurement Science Au) covering the bottom-up workflow from biochemistry basics to biological interpretation, maintained as a living tutorial at [proteomics-tutorial](https://jessegmeyerlab.github.io/proteomics-tutorial/). (open access)
- [A researcher's guide to mass spectrometry-based proteomics](https://doi.org/10.1002/pmic.201600113) - Overview (2016, Proteomics) of experimental design and workflow choices for newcomers to MS-based proteomics.
- [Data-independent acquisition-based SWATH-MS for quantitative proteomics: a tutorial](https://doi.org/10.15252/msb.20178126) - Tutorial by Ludwig et al. (2018, Molecular Systems Biology) on designing and analyzing DIA/SWATH-MS experiments. (open access)
- [R for Mass Spectrometry](https://rformassspectrometry.github.io/book/) - Online book teaching mass spectrometry and proteomics data handling and analysis with the R for Mass Spectrometry packages.

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

*Last Verified: Q2 2026*

> Instrument principles, ionization methods, mass analyzers, and data formats. Includes advanced MS applications (spatial proteomics, structural MS, HDX-MS, XL-MS, ion mobility, native MS) as sub-topics.

> Conceptual introductions to instrumentation and workflows are listed under [General Resources](#general-resources). The tools below help interpret spectra and plan experiments.

- [Protein Prospector](https://prospector.ucsf.edu/) - Web suite for MS-based sequence database searching with utilities (MS-Product, MS-Digest, MS-Isotope) for calculating fragment ions, in silico digests, and isotope patterns.
- [ChemCalc](https://www.chemcalc.org/) - Web toolset for calculating molecular masses, isotopic distributions, and peptide and protein fragmentation.
- [UW Proteomics Resource Tools](https://proteomicsresource.washington.edu/protocols06/) - Collection of online calculators for MS/MS fragmentation, in silico digestion, isotope distributions, and peptide masses.

### Advanced MS Applications

> Structural and specialized MS techniques: cross-linking (XL-MS), hydrogen-deuterium exchange (HDX-MS), thermal proteome profiling and CETSA, limited proteolysis (LiP-MS), ion mobility, and spatial proteomics.

- [pLink](https://github.com/pFindStudio/pLink2) - Search engine for identifying cross-linked peptides (XL-MS) with built-in false discovery rate control. `[GUI]` 🪟
- [xiSEARCH](https://www.rappsilberlab.org/software/xisearch/) - Search engine for cross-linked peptides supporting cleavable and non-cleavable cross-linkers, paired with the xiVIEW visualization tool. `[GUI]`
- [MeroX](https://www.stavrox.com/) - Software for identifying cross-linked peptides from MS-cleavable and non-cleavable cross-linkers. `[GUI]`
- [Kojak](https://www.kojak-ms.org/) - Open-source algorithm for identifying cross-linked peptides from tandem mass spectra. `[CLI]`
- [Deuteros 2.0](https://github.com/andymlau/Deuteros_2.0) - Open-source tool for processing, statistical analysis, and visualization of differential HDX-MS data. `[GUI]`
- [PyHDX](https://github.com/Jhsmit/PyHDX) - Python tool that derives residue-level protection factors and free energies from HDX-MS data. `[CLI]` `[API]`
- [TPP (Thermal Proteome Profiling)](https://bioconductor.org/packages/TPP) - R/Bioconductor package for analyzing thermal proteome profiling experiments across temperature or concentration ranges, including the NPARC model. `[CLI]`
- [mineCETSA](https://github.com/nkdailingyun/mineCETSA) - R package for processing and visualizing proteome-wide MS-CETSA target-engagement data. `[CLI]`
- [MSstatsLiP](https://bioconductor.org/packages/MSstatsLiP) - R/Bioconductor package for statistical analysis of limited proteolysis (LiP-MS) experiments at peptide and protein level. `[CLI]`
- [AlphaTims](https://github.com/MannLabs/alphatims) - Python package for fast access and visualization of Bruker timsTOF ion-mobility (TIMS-TOF) raw data. `[CLI]` `[API]`
- [pRoloc](https://bioconductor.org/packages/pRoloc) - R/Bioconductor framework using machine learning to assign proteins to subcellular compartments in spatial proteomics experiments, with the pRolocGUI visualization app. `[CLI]`

> Native and intact-protein MS deconvolution is covered by UniDec under [Top-Down Proteomics](#top-down-proteomics); diaPASEF ion-mobility DIA is supported within [FragPipe](#discovery-proteomics) and [DIA-NN](#dia-tools).

**[&uarr; Back to Contents](#contents)**

## Sample Preparation

*Last Verified: Q2 2026*

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

> Tissue and cell lysis, enrichment, and labeling steps are also handled within the suites under [Discovery Proteomics](#discovery-proteomics); PTM enrichment resources are listed under [Post-Translational Modifications](#post-translational-modifications).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Discovery Proteomics

*Last Verified: Q2 2026*

> Shotgun and bottom-up proteomics tools and resources. For intact-protein analysis see [Top-Down Proteomics](#top-down-proteomics); for computational analysis tools see also [Bioinformatics & Computational Tools](#bioinformatics--computational-tools).

- [MaxQuant](https://maxquant.org/) - Suite for label-free, SILAC, and isobaric quantification from shotgun data, built on the Andromeda search engine. `[DDA]` `[Label-Free]` `[TMT]` `[SILAC]` `[GUI]` 🪟
- [FragPipe](https://fragpipe.nesvilab.org/) - Graphical pipeline built on MSFragger for DDA, DIA, and labeling workflows. `[DDA]` `[DIA]` `[TMT]` `[GUI]`
- [PeptideShaker](https://github.com/compomics/peptide-shaker) - Search-engine-independent platform for interpreting and visualizing identification results from multiple engines. `[DDA]` `[GUI]`
- [SearchGUI](https://github.com/compomics/searchgui) - Graphical interface to configure and run several open-source search engines together. `[DDA]` `[GUI]`
- [AlphaPept](https://github.com/MannLabs/alphapept) - Modular Python framework for DDA analysis, accelerated with Numba, with a GUI, command line, and scriptable API. `[DDA]` `[Label-Free]` `[GUI]` `[CLI]` `[API]`
- [Proteome Discoverer](https://www.thermofisher.com/us/en/home/industrial/mass-spectrometry/liquid-chromatography-mass-spectrometry-lc-ms/lc-ms-software/multi-omics-data-analysis/proteome-discoverer-software.html) - Commercial, extensible platform for identification, quantification, and PTM analysis across DDA and DIA. `[DDA]` `[DIA]` `[TMT]` `[GUI]` 💰 🪟
- [PEAKS Studio](https://www.bioinfor.com/peaks-studio/) - Commercial suite combining de novo sequencing with database search for identification and quantification. `[DDA]` `[DIA]` `[GUI]` 💰 🪟
- [pFind](https://github.com/pFindStudio/pFind3) - Open-search engine (Open-pFind) for peptide identification, including unanticipated and unexpected modifications. `[DDA]` `[GUI]` 🪟

> Search engines that power discovery (MSFragger, Comet, Sage) are listed under [Bioinformatics > Identification](#identification).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Top-Down Proteomics

*Last Verified: Q2 2026*

> Analysis of intact proteins and proteoforms without digestion, preserving PTMs, isoforms, and sequence variants. Complements the peptide-centric workflows under [Discovery Proteomics](#discovery-proteomics), and covers both denatured and native (complex-down) approaches.

- [TopPIC Suite](https://www.toppic.org/) - Open-source suite (TopFD, TopPIC, TopMG, TopDiff, TopDIA) for proteoform identification, characterization, and quantification from top-down data. `[DDA]` `[DIA]` `[CLI]` `[GUI]`
- [Informed-Proteomics (MSPathFinder)](https://github.com/PNNL-Comp-Mass-Spec/Informed-Proteomics) - Open-source package with ProMex feature finding and the MSPathFinder database search engine for top-down LC-MS/MS. `[CLI]` 🪟
- [MASH Explorer](https://labs.wisc.edu/gelab/MASH_Explorer/index.php) - Free environment integrating multiple deconvolution and search algorithms for denatured and native top-down proteomics. `[GUI]` 🪟
- [ProSightPD](https://www.proteinaceous.net/prosightpd) - Commercial high-throughput top-down search platform running as nodes within Thermo Proteome Discoverer. `[GUI]` 💰 🪟
- [ProSight Lite](https://prosightlite.northwestern.edu/) - Free, vendor-agnostic tool for matching a single candidate proteoform and its modifications against fragmentation data. `[GUI]` 🪟
- [TDPortal](https://nrtdp.northwestern.edu/resource-software) - High-throughput, Galaxy-based top-down search system on HPC from the NRTDP, available to academic users on request. `[CLI]`
- [UniDec](https://github.com/michaelmarty/UniDec) - Bayesian deconvolution of intact-mass and ion-mobility spectra for native MS and intact protein analysis. `[GUI]` `[API]`
- [ClipsMS](https://github.com/loolab2020/ClipsMS) - Algorithm for assigning both terminal and internal fragment ions in top-down mass spectra to localize modifications along the protein sequence. `[CLI]`
- [Consortium for Top-Down Proteomics (CTDP)](https://ctdp.org/) - Nonprofit community advancing proteoform analysis, standards, the Human Proteoform Project, and the Proteoform Atlas data repository.

> Deconvolution is central to top-down; see also FLASHDeconv within [OpenMS](#pipelines--frameworks).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Quantitative Proteomics

*Last Verified: Q2 2026*

> DIA, targeted (SRM/PRM), and label-based quantification. Consolidates DIA and targeted approaches; will split via the [30/10 Rule](GOVERNANCE.md#the-3010-rule) when content density warrants it.

### DIA Tools

- [DIA-NN](https://github.com/vdemichev/DiaNN) - Automated software for library-free and library-based DIA quantification using deep learning. `[DIA]` `[Label-Free]` `[CLI]` 🐧 🪟
- [Spectronaut](https://biognosys.com/software/spectronaut/) - Commercial DIA analysis software supporting directDIA and spectral-library workflows. `[DIA]` `[GUI]` 💰
- [OpenSWATH](https://openms.readthedocs.io/en/latest/tutorials/knime-user-tutorial/openswath.html) - Targeted analysis of DIA and SWATH-MS data within the OpenMS ecosystem. `[DIA]` `[CLI]`
- [EncyclopeDIA](https://bitbucket.org/searleb/encyclopedia) - Library search engine for DIA using chromatogram and DDA-based spectral libraries. `[DIA]` `[GUI]`
- [DIAlignR](https://github.com/Roestlab/DIAlignR) - Retention time alignment across DIA, SWATH, PRM, and SRM runs for consistent quantification. `[DIA]` `[CLI]`
- [DIA-Umpire](https://github.com/Nesvilab/DIA-Umpire) - Untargeted DIA analysis that generates pseudo-MS/MS spectra for conventional database searching. `[DIA]` `[CLI]`

### Targeted / SRM / PRM

- [Skyline](https://skyline.ms/) - Open-source environment for building and analyzing SRM, PRM, targeted, and DIA assays. `[Targeted]` `[DIA]` `[GUI]` 🪟
- [Panorama](https://panoramaweb.org/) - Web repository and dashboard for targeted proteomics data built on Skyline documents. `[Targeted]` `[API]`
- [Avant-garde](https://github.com/SebVaca/Avant_garde) - Data-driven refinement of DIA and PRM signals by removing interfering transitions and scoring peaks. `[Targeted]` `[DIA]` `[CLI]`

### Label-Based Quantification (TMT, SILAC, iTRAQ)

> Isobaric and metabolic labeling is handled within the major suites; the entries below cover label-specific steps and statistics.

- [TMT-Integrator](https://fragpipe.nesvilab.org/) - Generates multi-level isobaric quantification reports, distributed with FragPipe. `[TMT]` `[CLI]`
- [MSstatsTMT](https://github.com/Vitek-Lab/MSstatsTMT) - R/Bioconductor package for protein-level statistical analysis of TMT experiments. `[TMT]` `[CLI]`
- [isobar](https://bioconductor.org/packages/isobar) - R/Bioconductor package for iTRAQ and TMT protein and peptide quantification with statistics. `[TMT]` `[CLI]`
- Core TMT and SILAC quantification is supported by [MaxQuant](#discovery-proteomics) and [FragPipe](#discovery-proteomics).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Post-Translational Modifications

*Last Verified: Q2 2026*

> Tools and resources organized by modification type. For unrestricted (open) modification discovery, see also the search engines under [Bioinformatics & Computational Tools](#bioinformatics--computational-tools).

&#x1F4D6; *Guide:* [PTM Analysis Strategy](guides/ptm-analysis-strategy.md) *(planned)*

### Phosphoproteomics

> Site localization, motif discovery, kinase-activity inference, and curated PTM knowledge bases.

- [PhosphoSitePlus](https://www.phosphosite.org/) - Curated knowledge base of experimentally observed phosphorylation, acetylation, ubiquitination, and methylation sites in human, mouse, and rat; free for academic and commercial use.
- [LuciPHOr2](http://luciphor2.sourceforge.net/) - Target-decoy site localization for generic modifications with false localization rate estimation from tandem MS data. `[CLI]`
- [onsite](https://github.com/bigbio/onsite) - Python package implementing the AScore, PhosphoRS, and LuciPHOr2 algorithms for phosphosite localization and scoring. `[CLI]` `[API]`
- [DeepMS2-phospho](https://github.com/lmsac/DeepMS2-phospho) - Deep learning prediction of phosphopeptide fragment spectra for spectral matching-based site localization. `[CLI]`
- [MoMo (MEME Suite)](https://meme-suite.org/meme/doc/momo.html) - Discovers sequence motifs associated with modification sites, reimplementing motif-x and MoDL with a web server and source code. `[CLI]`
- [KSEA App](https://github.com/casecpb/KSEA) - Kinase-Substrate Enrichment Analysis to infer changes in kinase activity from phosphoproteomics data; non-commercial use. `[CLI]`
- [KEA3](https://maayanlab.cloud/kea3/) - Web tool inferring upstream kinases whose putative substrates are enriched in a query protein or phosphoprotein list. `[API]`
- [PTM-SEA](https://github.com/broadinstitute/ssGSEA2.0) - PTM Signature Enrichment Analysis that scores site-level signatures from the PTMsigDB database. `[CLI]`

### Glycoproteomics

> Intact glycopeptide search engines and glycan structure knowledge bases.

- [pGlyco3](https://github.com/pFindStudio/pGlyco3) - Search engine for intact N- and O-glycopeptides and modified glycans with separate peptide and glycan FDR control. `[GUI]` 🪟
- [GlycReSoft](https://github.com/mobiusklein/glycresoft) - Command-line search engine for glycomics and glycoproteomics LC-MS/MS data. `[CLI]`
- [StrucGP](https://github.com/Sun-GlycoLab/StrucGP) - Database-independent search engine for structural interpretation of N-glycans on intact glycopeptides. `[GUI]` 🪟
- [StrucGAP](https://github.com/Sun-GlycoLab/StrucGAP) - Python platform for downstream structural and site-specific glycoproteomics analysis, covering preprocessing, quantification, network visualization, and annotation across multiple search engines. `[CLI]` `[API]`
- [Byonic](https://www.proteinmetrics.com/products/byonic) - Commercial search engine for peptide, protein, and glycopeptide identification supporting wide PTM searches. `[GUI]` 💰
- [pGlycoQuant](https://github.com/Power-Quant/pGlycoQuant) - Quantification tool for intact glycopeptides that works with pGlyco3 and other search results. `[CLI]`
- [GlyTouCan](https://glytoucan.org/) - International glycan structure repository that assigns globally unique accession numbers to registered glycans.
- [GlyConnect](https://glyconnect.expasy.org/) - Database of glycosylation sites, glycan structures, and associated proteins on the SIB ExPASy portal.
- [GlyGen](https://www.glygen.org/) - Integrated knowledge base unifying glycan, glycoprotein, and glycosylation data from multiple sources.
- [GlyCosmos](https://glycosmos.org/) - Web portal integrating glycan structures, glycogenes, glycoproteins, pathways, and related repositories.

> Glyco workflows are also built into [FragPipe](#discovery-proteomics) (MSFragger-Glyco) and [MetaMorpheus](#pipelines--frameworks) (O-Pair Search).

### Ubiquitination & Other PTMs

> Open-search modification characterization and cross-modification reference databases.

- [PTM-Shepherd](https://github.com/Nesvilab/PTM-Shepherd) - Characterizes and summarizes PTM profiles from open searches using localization, spectral similarity, retention time, and modification rates. `[CLI]`
- [MSstatsPTM](https://bioconductor.org/packages/MSstatsPTM) - R/Bioconductor package for statistical analysis of PTM-site abundance that adjusts for changes in overall protein levels, supporting DDA, DIA, SRM, and TMT data. `[CLI]`
- [dbPTM](https://biomics.lab.nycu.edu.tw/dbPTM/) - Integrated database of experimentally verified and predicted PTM sites with functional and structural annotation.
- [iPTMnet](https://research.bioinformatics.udel.edu/iptmnet/) - Bioinformatics resource integrating PTM sites, modifying enzymes, and substrate relationships for systems biology.
- [Unimod](https://www.unimod.org/) - Reference of protein modifications and their mass shifts for mass spectrometry, maintained with the HUPO-PSI.

> Unrestricted modification discovery is provided by [MSFragger](#identification), [pFind](#discovery-proteomics) (Open-pFind), and [MetaMorpheus](#pipelines--frameworks) (G-PTM-D); ubiquitin diGly remnant profiling is supported within [MaxQuant](#discovery-proteomics) and [FragPipe](#discovery-proteomics).

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Single-Cell Proteomics

*Last Verified: Q2 2026*

> Tools and resources for single-cell and low-input proteomics. Entries require documentation and at least one published use case.

&#x1F4D6; *Guide:* [Single-Cell Best Practices](guides/single-cell-best-practices.md) *(planned)*

- [scp](https://bioconductor.org/packages/scp) - Bioconductor package for processing and analyzing mass spectrometry-based single-cell proteomics data. `[CLI]`
- [SCeptre](https://github.com/bfurtwa/SCeptre) - Python package that extends Scanpy to analyze multiplexed single-cell proteomics data. `[CLI]`
- [SCP resources (Slavov Lab)](https://scp.slavovlab.net/) - Community hub for single-cell proteomics methods, protocols, datasets, and reporting guidelines.
- [Single-Cell Proteomics Conference](https://single-cell.net/) - Annual conference with an open archive of recorded talks and community guidelines.
- [Focus on single-cell proteomics (Nature Methods)](https://www.nature.com/collections/bdfhafhdeb) - Curated Nature Methods collection of articles on single-cell proteomics methods, challenges, and applications.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Bioinformatics & Computational Tools

*Last Verified: Q2 2026*

> **The backbone of this list.** Computational tools for proteomics data analysis, organized by function. Capability tags help you find what works with your data and platform.

**Essential tools** (see full entries in the relevant sections):

- [MaxQuant](https://maxquant.org/) - Quantitative proteomics software for analyzing large mass spectrometric data sets. `[DDA]` `[Label-Free]` `[TMT]` `[SILAC]` &#x1F5A5;&#xFE0F;
- [MSFragger](https://msfragger.nesvilab.org/) - Fragment-ion indexing database search engine for peptide identification. `[DDA]` `[DIA]` `[CLI]`
- [DIA-NN](https://github.com/vdemichev/DiaNN) - Deep neural network-based software for DIA and DDA proteomics. `[DIA]` `[DDA]` `[Label-Free]` `[CLI]`

<details>
<summary><b>Sub-section index</b> (click to expand)</summary>
<br>

| Sub-section                                      | What it covers                                     |
| ------------------------------------------------ | -------------------------------------------------- |
| [Identification](#identification)                | Search engines, spectral libraries, rescoring      |
| [Quantification](#quantification)                | Label-free, isobaric, metabolic labeling tools     |
| [Statistical Analysis](#statistical-analysis)    | Differential expression, imputation, normalization |
| [Visualization](#visualization)                  | Plots, interactive dashboards, spectrum viewers    |
| [Quality Control](#quality-control)              | Run monitoring, QC metrics, batch effects          |
| [Pipelines & Frameworks](#pipelines--frameworks) | End-to-end analysis platforms                      |
| [Cloud & HPC](#cloud--hpc)                       | nf-core, Galaxy, Nextflow/Snakemake tooling        |

</details>

### Identification

- [MSFragger](https://msfragger.nesvilab.org/) - Fragment-ion indexing database search engine for closed and open (mass-tolerant) peptide identification. `[DDA]` `[DIA]` `[CLI]`
- [Comet](https://uwpr.github.io/Comet/) - Open-source tandem mass spectrometry database search engine derived from the SEQUEST algorithm. `[DDA]` `[CLI]`
- [Sage](https://github.com/lazear/sage) - Cross-platform search engine in Rust with built-in quantification, rescoring, and FDR control. `[DDA]` `[CLI]` 🐧 🪟 🍎
- [Percolator](http://percolator.ms/) - Semi-supervised post-processor that rescores peptide-spectrum matches and controls FDR. `[CLI]`
- [mokapot](https://github.com/wfondrie/mokapot) - Flexible Python reimplementation of the Percolator rescoring algorithm. `[CLI]` `[API]`
- [MS-GF+](https://github.com/MSGFPlus/msgfplus) - Database search engine that uses a generating-function scoring approach and supports many instrument types and fragmentation methods. `[DDA]` `[CLI]`
- [Crux](https://crux.ms/) - Cross-platform toolkit bundling the Tide search engine, Percolator, and label-free quantification. `[DDA]` `[CLI]` 🐧 🪟 🍎

### Quantification

- [MaxQuant](https://maxquant.org/) - See [Discovery Proteomics](#discovery-proteomics) for the full entry. Andromeda-based suite with label-free, SILAC, and TMT quantification.
- [IonQuant](https://github.com/Nesvilab/IonQuant) - Label-free and isobaric quantification with match-between-runs and FDR control, used within the FragPipe ecosystem. `[Label-Free]` `[TMT]` `[CLI]`
- [FlashLFQ](https://github.com/smith-chem-wisc/FlashLFQ) - Label-free quantification engine with match-between-runs, usable standalone or within MetaMorpheus. `[Label-Free]` `[CLI]`
- [directLFQ](https://github.com/MannLabs/directlfq) - Label-free protein quantification using a ratio-based algorithm that scales linearly to very large sample cohorts. `[Label-Free]` `[CLI]` `[API]`
- [Triqler](https://github.com/statisticalbiotechnology/triqler) - Probabilistic model that propagates identification and quantification error into protein-level fold changes. `[CLI]`

### Statistical Analysis

- [MSstats](https://msstats.org/) - R/Bioconductor package for statistical relative quantification across label-free, DIA, and labeled experiments. `[CLI]`
- [DEqMS](https://bioconductor.org/packages/DEqMS) - Differential expression analysis that models PSM-count-dependent variance in quantitative proteomics. `[CLI]`
- [limma](https://bioconductor.org/packages/limma) - Linear-models package for differential expression, originally developed for microarrays and applicable to proteomics intensity data. `[CLI]`
- [Perseus](https://maxquant.net/perseus/) - Graphical platform for downstream statistical analysis of proteomics matrices. `[GUI]` 🪟
- [msqrob2](https://bioconductor.org/packages/msqrob2) - Robust linear mixed model framework for differential abundance, including missing-data-aware workflows. `[CLI]`
- [proDA](https://github.com/const-ae/proDA) - Differential abundance analysis with a probabilistic dropout model that handles missing values without imputation. `[CLI]`
- [protti](https://github.com/jpquast/protti) - R package for quality control and analysis of bottom-up and LiP-MS data, working with output from Spectronaut, MaxQuant, Proteome Discoverer, and Skyline. `[CLI]`

### Visualization

- [Cytoscape](https://cytoscape.org/) - Platform for visualizing molecular interaction networks and integrating them with expression data. `[GUI]`
- [spectrum_utils](https://github.com/bittremieux/spectrum_utils) - Python package for processing and visualizing tandem mass spectra. `[API]`
- [PDV](https://github.com/wenbostar/PDV) - Graphical viewer for proteomics data including spectra, chromatograms, and identification results. `[GUI]`
- [IPSA (Interactive Peptide Spectral Annotator)](https://github.com/coongroup/IPSA) - Web-based annotator that generates interactive, exportable visualizations of peptide tandem mass spectra. `[GUI]`
- [ComplexHeatmap](https://github.com/jokergoo/ComplexHeatmap) - R/Bioconductor package for generating annotated heatmaps, applied to proteomics expression matrices. `[API]`
- [clusterProfiler](https://github.com/YuLab-SMU/clusterProfiler) - Enrichment and GSEA tool with visualization for interpreting protein and gene lists across many ontologies and species. `[API]`
- [fgsea](https://bioconductor.org/packages/fgsea) - R/Bioconductor package for preranked gene set enrichment analysis that estimates low enrichment p-values using a multilevel Monte Carlo scheme. `[CLI]`

### Quality Control

- [RawTools](https://github.com/kevinkovalchik/RawTools) - Extraction of QC metrics and quantification information directly from Thermo raw files. `[CLI]`
- [rawrr](https://bioconductor.org/packages/rawrr) - R package for reading Thermo raw files directly for diagnostics and QC. `[CLI]`
- [PTXQC](https://github.com/cbielow/PTXQC) - R package generating quality control reports from MaxQuant output. `[CLI]`
- [rawDiag](https://github.com/fgcz/rawDiag) - R package producing diagnostic plots from raw files to support rational LC-MS method optimization. `[CLI]`

### Pipelines & Frameworks

- [FragPipe](https://fragpipe.nesvilab.org/) - See [Discovery Proteomics](#discovery-proteomics). GUI pipeline integrating MSFragger, IonQuant, and Philosopher.
- [OpenMS](https://www.openms.de/) - Open-source C++/Python framework with composable tools for building MS workflows. `[CLI]` `[API]` 🐧 🪟 🍎
- [MetaMorpheus](https://github.com/smith-chem-wisc/MetaMorpheus) - Search and analysis platform supporting PTM discovery (G-PTM-D), calibration, and quantification. `[DDA]` `[GUI]` `[CLI]`
- [pyteomics](https://github.com/levitsky/pyteomics) - Python framework for reading proteomics data formats and performing common computations. `[API]`
- [Philosopher](https://philosopher.nesvilab.org/) - Toolkit wrapping the Trans-Proteomic Pipeline for validation, inference, FDR filtering, and quantification. `[CLI]`
- [Trans-Proteomic Pipeline (TPP)](http://www.tppms.org/) - Open-source suite covering identification, validation, quantification, and visualization. `[CLI]` `[GUI]`
- [MSnbase](https://bioconductor.org/packages/MSnbase) - R/Bioconductor infrastructure for manipulation, processing, and visualization of MS data. `[API]`
- [MS-DAP](https://github.com/ftwkoopmans/msdap) - Downstream analysis pipeline for label-free proteomics that standardizes quality control, normalization, and differential expression across upstream tools such as MaxQuant, DIA-NN, FragPipe, and Spectronaut. `[CLI]` `[API]` 📦
- [Ursgal](https://github.com/ursgal/ursgal) - Python module providing a unified interface to run, combine, and post-process results from multiple bottom-up search engines. `[CLI]` `[API]`

### Cloud & HPC

- [nf-core/quantms](https://github.com/bigbio/quantms) - Nextflow pipeline for reproducible DDA-LFQ, TMT, and DIA-LFQ quantification at scale. `[DIA]` `[TMT]` `[Label-Free]` `[CLI]` 📦
- [Galaxy Proteomics (usegalaxy.eu)](https://proteomics.usegalaxy.eu/) - Dedicated European Galaxy proteomics server (Galaxy-P) hosting MS proteomics and proteogenomics tools and workflows that run in the browser without local installation. `[GUI]`
- [Sage](https://github.com/lazear/sage) - See [Identification](#identification). Cloud-ready Rust engine that streams data directly from S3 for large-scale searches.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## AI & Machine Learning in Proteomics

*Last Verified: Q2 2026*

> Machine learning and deep learning applied to proteomics. Entries require a working repository with documentation.

- [Prosit](https://www.proteomicsdb.org/prosit/) - Deep learning models for fragment intensity and retention time prediction, used for spectral libraries and rescoring. `[API]`
- [DeepLC](https://github.com/compomics/DeepLC) - Retention time prediction for peptides, including modified peptides not seen during training. `[CLI]` `[API]`
- [Casanovo](https://github.com/Noble-Lab/casanovo) - Transformer model for de novo peptide sequencing from MS/MS spectra. `[CLI]` 🧪
- [MSBooster](https://github.com/Nesvilab/MSBooster) - Adds deep-learning-predicted features (spectra, retention time) to rescore peptide identifications. `[CLI]`
- [Oktoberfest](https://github.com/wilhelm-lab/oktoberfest) - Open-source Prosit-based pipeline for collision energy calibration, rescoring, and spectral library generation. `[CLI]`
- [MS2PIP](https://github.com/compomics/ms2pip) - Machine-learning predictor of peptide fragmentation spectra for spectral libraries and rescoring. `[CLI]` `[API]`
- [MS2Rescore](https://github.com/compomics/ms2rescore) - Modular rescoring framework that adds predicted features to boost peptide identifications. `[CLI]`
- [InstaNovo](https://github.com/instadeepai/InstaNovo) - De novo peptide sequencing combining a transformer model (InstaNovo) with a diffusion model (InstaNovo+) that refines predicted sequences by iterative decoding. `[CLI]` 🧪

### Foundation Models / Protein Language Models (pLMs)

> Spectrum prediction (Prosit, Koina), retention time prediction, protein representation learning (ESM, ProtTrans), and AlphaFold integrations applied to MS data.

&#x1F4D6; *Guide:* [AI/ML in Proteomics](guides/ai-ml-in-proteomics.md) *(planned)*

- [Koina](https://koina.wilhelmlab.org/) - Open service and API network that serves many proteomics ML models (Prosit, AlphaPeptDeep, and more) for prediction and rescoring. `[API]` 📦
- [AlphaPeptDeep](https://github.com/MannLabs/alphapeptdeep) - Deep learning framework for building MS2, retention time, and collision cross section prediction models. `[CLI]` `[API]`
- [ESM (Evolutionary Scale Modeling)](https://github.com/evolutionaryscale/esm) - Protein language models (ESM-2 and ESMFold, plus the newer ESM3 and ESMC) for sequence representation, structure-aware embeddings, and structure prediction; the original facebookresearch/esm repository is now archived. `[API]`
- [ProtTrans](https://github.com/agemagician/ProtTrans) - Collection of pretrained protein language models for transfer learning on protein sequences. `[API]`
- [AlphaFold](https://github.com/google-deepmind/alphafold) - Protein structure prediction models, from AlphaFold2 to the newer AlphaFold3 ([source](https://github.com/google-deepmind/alphafold3), released for non-commercial use), increasingly integrated with MS-based proteomics workflows. `[CLI]`
- [ColabFold](https://github.com/sokrypton/ColabFold) - Protein structure prediction that accelerates AlphaFold2 and ESMFold by replacing the MSA step with MMseqs2 search, runnable in Google Colab or on the command line. `[CLI]` `[API]`

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Data Repositories & Standards

*Last Verified: Q2 2026*

> Public repositories, data standards, controlled vocabularies, and format specifications.

&#x1F4D6; *Guides:* [File Format Cheat Sheet](guides/file-format-cheat-sheet.md) &middot; [Tool Compatibility Matrix](guides/compatibility-matrix.md) *(planned)*

- [CPTAC / Proteomic Data Commons](https://pdc.cancer.gov/) - Repository for harmonized cancer proteogenomic datasets from the CPTAC program.
- [HUPO-PSI Standards](https://www.psidev.info/) - Community data standards and controlled vocabularies (mzML, mzIdentML, mzTab, and more).
- [iProX](https://www.iprox.cn/) - ProteomeXchange member repository in China for raw data, analysis results, and metadata.
- [jPOST](https://jpostdb.org/) - Japan-based ProteomeXchange repository with a curated, reprocessed database layer.
- [MassIVE](https://massive.ucsd.edu/) - Repository for MS proteomics data with reanalysis and dataset-derived spectral libraries.
- [ppx](https://github.com/wfondrie/ppx) - Python interface to find and download files and metadata from ProteomeXchange repositories. `[CLI]` `[API]`
- [PRIDE](https://www.ebi.ac.uk/pride/) - Repository for mass spectrometry proteomics data hosted at EMBL-EBI, and a founding member of the ProteomeXchange consortium.
- [ProteomeXchange](http://www.proteomexchange.org/) - Consortium providing a single point of submission and access across major proteomics repositories.
- [ProteoWizard](https://proteowizard.sourceforge.io/) - Cross-platform libraries and tools (including msconvert) for converting and processing raw vendor data. `[CLI]` `[GUI]` 🐧 🪟 🍎
- [ThermoRawFileParser](https://github.com/compomics/ThermoRawFileParser) - Cross-platform converter from Thermo raw files to open formats such as mzML and MGF. `[CLI]` 🐧 🪟 🍎

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Protein Databases & Knowledge Bases

*Last Verified: Q2 2026*

> Protein sequence, structure, family, function, enzyme, pathway, interaction, disease, and proteoform databases. Includes general biological knowledge bases beyond proteomics that are widely used in proteomics research. For data submission and reanalysis repositories see [Data Repositories & Standards](#data-repositories--standards).

### Sequence & Function Knowledge Bases

- [Ensembl](https://www.ensembl.org/) - Integrates genome annotation across vertebrate and other eukaryotic species, providing gene, transcript, and protein sequences with cross-references used to map proteomics identifiers.
- [GeneCards](https://www.genecards.org/) - Aggregates gene-centric genomic, transcriptomic, proteomic, and disease information for human genes from many integrated sources.
- [HGNC](https://www.genenames.org/) - Assigns approved, unique symbols and names for human genes and their protein products to provide stable identifiers for cross-referencing.
- [NCBI RefSeq](https://www.ncbi.nlm.nih.gov/refseq/) - Provides a curated, non-redundant collection of reference genomic, transcript, and protein sequences used for annotation and as proteomics search databases.
- [neXtProt](https://www.expasy.org/archives/nextprot) - Integrates human protein sequence, expression, interaction, PTM, and variant data; reached end of life in 2024 after 14 years, with its data and tools archived on Expasy and still downloadable.
- [UniParc](https://www.uniprot.org/uniparc) - Maintains a non-redundant archive of protein sequences from public databases, retaining sequences removed from UniProtKB.
- [UniProt](https://www.uniprot.org/) - Provides protein sequences and functional annotation through the manually reviewed Swiss-Prot and automatically annotated TrEMBL sections of UniProtKB.
- [UniProt Proteomes](https://www.uniprot.org/proteomes) - Provides per-organism protein sets for species with sequenced genomes, used as reference search databases in proteomics (human reference proteome UP000005640).
- [UniRef](https://www.uniprot.org/uniref) - Provides clustered sequence sets (UniRef100, UniRef90, UniRef50) that reduce redundancy for faster similarity searches and profile building.

> Note: Starting with release 2025_04 (October 2025) and completing with release 2026_02 (mid-2026), UniProtKB is being reduced to proteins from reference proteomes, plus reviewed Swiss-Prot entries and entries of high biological relevance; removed sequences remain searchable and downloadable in UniParc.

### Structure Databases

- [AlphaFold Protein Structure Database](https://alphafold.ebi.ac.uk/) - Provides over 214 million predicted protein structures from AlphaFold, developed by Google DeepMind and EMBL-EBI under a CC-BY-4.0 licence.
- [CATH](https://www.cathdb.info/) - Classifies protein domain structures from the PDB into a hierarchy of class, architecture, topology, and homologous superfamily.
- [DisProt](https://disprot.org/) - Curates experimentally validated intrinsically disordered proteins and regions with manual structural and functional annotations from the literature.
- [MobiDB](https://mobidb.org/) - Annotates intrinsically disordered proteins and regions by combining curated annotations, indirect structural evidence, and sequence-based predictions.
- [PDBe (Protein Data Bank in Europe)](https://www.ebi.ac.uk/pdbe/) - Provides the European wwPDB access point for macromolecular structures with search, analysis, and Mol* visualization services.
- [RCSB Protein Data Bank (PDB)](https://www.rcsb.org/) - Provides the US access point to experimentally determined 3D structures of proteins, nucleic acids, and complexes archived by the wwPDB.
- [SCOP](https://www.ebi.ac.uk/pdbe/scop/) - Classifies protein domains of known structure into families, superfamilies, and folds based on structural and evolutionary relationships.

### Families, Domains & Ontologies

- [ELM (Eukaryotic Linear Motif resource)](http://elm.eu.org/) - Annotates and predicts short linear motifs that mediate protein interactions and regulation in eukaryotic proteins.
- [Gene Ontology (GO)](https://geneontology.org/) - Provides a controlled vocabulary and annotations describing protein molecular functions, biological processes, and cellular components.
- [InterPro](https://www.ebi.ac.uk/interpro/) - Classifies proteins into families and predicts domains and functional sites by integrating signatures from multiple member databases.
- [PANTHER](https://www.pantherdb.org/) - Classifies proteins by family, subfamily, molecular function, biological process, and pathway using phylogenetic trees.
- [Pfam](https://www.ebi.ac.uk/interpro/entry/pfam/) - Provides protein families represented by multiple sequence alignments and hidden Markov models, now hosted within InterPro.
- [PROSITE](https://prosite.expasy.org/) - Documents protein domains, families, and functional sites with patterns and profiles, complemented by ProRule annotation rules.
- [SMART](https://smart.embl.de/) - Identifies and annotates protein domains and analyzes domain architectures using manually curated domain models.

### Enzymes & Peptidases

- [BRENDA](https://www.brenda-enzymes.org/) - Provides functional enzyme data including kinetics, substrates, reactions, and organisms organized by EC classification; free under a CC-BY-4.0 licence.
- [CAZy](https://www.cazy.org/) - Classifies carbohydrate-active enzymes into sequence-based families that link sequence to structure, mechanism, and specificity.
- [MEROPS](https://www.ebi.ac.uk/merops/) - Classifies peptidases (proteases), their inhibitors, and substrates into a structure-based hierarchy of families and clans.
- [TopFIND](https://topfind.clip.msl.ubc.ca/) - Knowledge base of protein termini, their generation by proteases, and the functional implications, integrating curated and community-contributed cleavage and processing data with the TopFINDer and PathFINDer analysis tools.

### Pathways & Interactions

- [BioGRID](https://thebiogrid.org/) - Curates protein, genetic, and chemical interactions and post-translational modifications from published literature.
- [Complex Portal](https://www.ebi.ac.uk/complexportal) - Provides manually curated macromolecular complexes for key model organisms, supplemented by machine-learning-predicted human complexes.
- [CORUM](https://mips.helmholtz-muenchen.de/corum/) - Provides manually curated, experimentally characterized mammalian protein complexes with composition, function, and localization.
- [GeneMANIA](https://genemania.org/) - Predicts gene and protein function by integrating association networks from co-expression, interaction, and pathway data.
- [IntAct](https://www.ebi.ac.uk/intact/) - Provides molecular interactions from literature curation and direct submissions, and produces the Complex Portal.
- [KEGG](https://www.genome.jp/kegg/) - Provides manually drawn pathway maps linking genes and proteins to metabolism, signaling, and disease; web access is free for academic use while bulk downloads require a license.
- [MINT](https://mint.bio.uniroma2.it/) - Stores experimentally verified protein-protein interactions curated from the literature, integrated with IntAct under the IMEx consortium.
- [Pathway Commons](https://www.pathwaycommons.org/) - Aggregates pathway and molecular interaction data from many source databases into a single resource queryable in BioPAX format.
- [Reactome](https://reactome.org/) - Provides curated, peer-reviewed biological pathways with tools for visualization and enrichment analysis.
- [SIGNOR](https://signor.uniroma2.it/) - Stores manually curated causal signaling interactions, including phosphorylation events, as customizable directional networks.
- [STRING](https://string-db.org/) - Provides known and predicted protein-protein associations integrating experimental, computational, and literature evidence with enrichment and clustering tools.
- [WikiPathways](https://www.wikipathways.org/) - Provides an open, community-curated collection of biological pathways available for download and enrichment analysis.

### Disease, Drug & Target Knowledge Bases

- [ChEMBL](https://www.ebi.ac.uk/chembl/) - Provides manually curated bioactivity data linking drug-like molecules to protein targets under a CC-BY-SA licence.
- [DisGeNET](https://www.disgenet.com/) - Integrates gene-disease and variant-disease associations from curated databases and text mining; now distributed under a freemium model requiring registration. 💰
- [DrugBank](https://go.drugbank.com/) - Provides drug, drug-target, mechanism, and interaction data; free for academic use under license with commercial tiers. 💰
- [OMIM](https://www.omim.org/) - Catalogs human genes and genetic disorders with curated gene-to-phenotype relationships from the biomedical literature.
- [Open Targets Platform](https://platform.opentargets.org/) - Integrates genetic, omics, and literature evidence to score and prioritize therapeutic targets for diseases.
- [Pharos](https://pharos.nih.gov/) - Presents target, disease, and ligand data from the Illuminating the Druggable Genome program with emphasis on understudied human proteins.

### Expression & Proteoform Atlases

- [Blood Proteoform Atlas](https://blood-proteoform-atlas.org/) - Provides a reference map of proteoforms across human hematopoietic cell types in blood and bone marrow.
- [Expression Atlas](https://www.ebi.ac.uk/gxa/home) - Provides gene and protein expression results across tissues, cell types, and conditions from curated RNA-seq and proteomics studies.
- [GTEx Portal](https://gtexportal.org/home/) - Provides tissue-specific gene expression and regulatory data across human tissues from a large donor cohort.
- [Human Protein Atlas](https://www.proteinatlas.org/) - Maps human protein expression and subcellular localization across tissues, cells, organs, and blood using imaging, mass spectrometry, and transcriptomics.
- [Human Proteoform Atlas](https://human-proteoform-atlas.org/) - Provides experimentally verified human proteoforms, descended from the Consortium for Top-Down Proteomics Proteoform Atlas.
- [Human Proteome Map](https://www.humanproteomemap.org/) - Provides a draft map of human protein expression across adult and fetal tissues from the Kim et al. proteome study.
- [PeptideAtlas](https://peptideatlas.org/) - Provides a multi-organism compendium of peptides identified across uniformly reprocessed tandem MS datasets.
- [ProteomicsDB](https://www.proteomicsdb.org/) - Provides a knowledge base of protein expression and related multi-omics measurements, and hosts the Prosit prediction service.
- [SRMAtlas](https://srmatlas.org/) - Provides targeted SRM/MRM assays built from synthetic peptides to detect and quantify proteins across complete proteomes.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Multi-Omics Integration

*Last Verified: Q2 2026*

> Tools for integrating proteomics with genomics, transcriptomics, and metabolomics. Focus on proteomics-centric or proteomics-aware integrations.

- [MOFA+ / MOFA2](https://biofam.github.io/MOFA2/) - Unsupervised factor-analysis framework that integrates multiple omics layers into shared, interpretable latent factors. `[CLI]` `[API]`
- [mixOmics](https://mixomics.org/) - R package of multivariate methods for omics exploration and integration, including the DIABLO supervised multi-omics framework. `[CLI]`
- [WGCNA](https://cran.r-project.org/package=WGCNA) - R package for weighted correlation network analysis that finds co-expression modules and relates them to sample traits. `[CLI]`
- [COSMOS](https://saezlab.github.io/cosmosR/) - Integrates phosphoproteomics, transcriptomics, and metabolomics with prior-knowledge networks to infer causal mechanistic hypotheses. `[CLI]`
- [OmicsAnalyst](https://www.omicsanalyst.ca/) - Web platform for statistical, visual, and network-based integration of multiple omics datasets.
- [LinkedOmics](https://www.linkedomics.org/) - Web portal to access and correlate multi-omics data, including CPTAC proteomics, across TCGA and CPTAC cancer cohorts.
- [muon](https://muon.scverse.org/) - Python framework built on the MuData structure for multimodal single-cell and multi-omics analysis. `[API]`
- [mogsa](https://bioconductor.org/packages/mogsa) - R/Bioconductor package for multi-omics integrative clustering (moCluster) and single-sample multi-omics gene set analysis. `[CLI]`
- [lipidr](https://bioconductor.org/packages/lipidr) - R/Bioconductor package for import, quality control, differential analysis, and visualization of targeted and untargeted lipidomics data. `[CLI]`

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Frontier & Niche Techniques

*Last Verified: Q2 2026*

> Emerging and specialized proteomics approaches. Honest about sparsity; entries grow as fields mature.

### Metaproteomics

- [Unipept](https://unipept.ugent.be/) - Web application, API, and command-line tools for taxonomic and functional analysis of metaproteomics peptides. `[GUI]` `[CLI]` `[API]`
- [MetaLab](https://imetalab.ca/) - Automated platform for metaproteomic identification, quantification, and taxonomic and functional annotation, supporting DDA and DIA data. `[GUI]` 🪟
- [MetaProteomeAnalyzer (MPA)](https://github.com/compomics/meta-proteome-analyzer) - Open-source tool that identifies metaproteomics data and groups results into taxonomic and functional meta-proteins. `[GUI]` `[CLI]`

### Proteogenomics

- [Galaxy-P](https://galaxyp.org/) - Galaxy-based multi-omics platform with workflows for building custom sequence databases and performing proteogenomic analysis. `[GUI]`
- [customProDB](https://bioconductor.org/packages/customProDB) - R/Bioconductor package that builds customized protein databases from RNA-seq data for proteomics search. `[CLI]`
- [Spritz](https://smith-chem-wisc.github.io/Spritz/) - Software that builds sample-specific proteoform databases annotated with sequence variants and PTMs from RNA-seq data. `[GUI]` 🪟

### Other Emerging Approaches

> Immunopeptidomics and interaction (AP-MS) proteomics.

- [MHCquant](https://nf-co.re/mhcquant/) - Nextflow/nf-core pipeline for identifying and quantifying MHC-presented (immunopeptidomics) peptides, built on OpenMS. `[CLI]` 📦
- [SAINTexpress](https://saint-apms.sourceforge.net/) - Tool that assigns confidence scores to protein-protein interactions from affinity purification-mass spectrometry (AP-MS) data. `[CLI]`
- [CRAPome / RePRINT](https://reprint-apms.org/) - Contaminant repository of negative-control AP-MS data used to estimate background and filter interaction candidates.

<!-- More entries welcome. See CONTRIBUTING.md -->

**[&uarr; Back to Contents](#contents)**

## Community & Organizations

*Last Verified: Q2 2026*

> Professional societies, community channels, conferences, and organizations.

- [ASMS (American Society for Mass Spectrometry)](https://www.asms.org/) - Mass spectrometry society, publisher of the Journal of the American Society for Mass Spectrometry (JASMS) and host of the annual ASMS Conference.
- [Biostars](https://www.biostars.org/) - Question-and-answer forum for bioinformatics, with an active community discussing proteomics data analysis.
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

## Deprecated / Legacy

> Tools that are no longer maintained but were historically important. Each entry includes what replaced it and why it mattered. See [CONTRIBUTING.md](CONTRIBUTING.md) for the obituary format.

<!-- Format: ~~[Tool Name](url)~~ - Superseded by [Successor](url). Original contribution: X. Last usable version: vN.N (YYYY). -->

- ~~[PGA](https://github.com/wenbostar/PGA)~~ - Superseded by [customProDB](https://bioconductor.org/packages/customProDB) and [ProteoDisco](https://bioconductor.org/packages/ProteoDisco). Original contribution: an R/Bioconductor proteogenomics package that built customized protein databases from RNA-seq data with integrated database searching, post-processing, and report generation. Last available in Bioconductor 3.11 (2020) and removed from Bioconductor 3.12; last GitHub release v1.9.1 (2017).

**[&uarr; Back to Contents](#contents)**

---

## Guides & Workflows

This repository has two companion directories for content that goes beyond a link list:

| Directory    | What it contains                                                                              | Browse                      |
| ------------ | --------------------------------------------------------------------------------------------- | --------------------------- |
| `guides/`    | Opinionated expert deep-dives, decision trees, comparison tables, and mini-guides (500 words) | [All Guides](guides/)       |
| `workflows/` | Practitioner start-to-finish pipelines with Nextflow/Snakemake snippets                       | [All Workflows](workflows/) |

**Published guides:** [Beginner's Guide](guides/beginners-guide.md) &middot; [File Format Cheat Sheet](guides/file-format-cheat-sheet.md)

**Planned guides:** [Tool Compatibility Matrix](guides/compatibility-matrix.md) &middot; [Starter Packs](guides/starter-packs.md) &middot; [DIA Tools Comparison](guides/dia-tools-comparison.md)

**Planned workflows:** [Label-Free DDA](workflows/label-free-dda.md) &middot; [DIA Analysis](workflows/dia-analysis.md) &middot; [Phosphoproteomics](workflows/phosphoproteomics.md) &middot; [Single-Cell](workflows/single-cell.md)

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
