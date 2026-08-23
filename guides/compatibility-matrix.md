---
title: "Tool Compatibility Matrix"
status: current
author: "@eneskemalergin"
last_reviewed: 2026-06-07
tags: [reference, tools, compatibility, vendor-formats, file-formats]
related:
  - beginners-guide.md
  - file-format-cheat-sheet.md
---

# Tool Compatibility Matrix

Which analysis tool can open which vendor's raw data, and on which operating system? This is one of the first practical questions in any project, because the answer decides whether you can search your files as-is or have to convert them first.

This page collects what the tool authors document, cross-checked against vendor sources. When a tool's own docs and a third-party claim disagree, the tool's own documentation wins here.

> **How to use this matrix:** find the format you have (a column), then read down to see which tools read it natively. A 🔄 means "convert to `mzML` first" - see the [File Format Cheat Sheet](file-format-cheat-sheet.md) for what each format is and how to convert it.

## TL;DR

- **Thermo `.raw`** is the most broadly supported native format - almost every modern tool reads it directly.
- **Bruker timsTOF `.d`** is read natively by the major DIA/timsTOF-aware tools (DIA-NN, FragPipe, MaxQuant, Spectronaut, Skyline, PEAKS).
- **SCIEX `.wiff`, Agilent `.d`, and Waters `.raw`** have narrower native support; outside a few tools you convert them to `mzML` first.
- **`mzML` is the universal fallback.** If a tool reads nothing else you have, convert to `mzML` and every search engine here will take it.
- **On Linux/macOS**, native vendor reading is limited. Thermo `.raw` and Bruker `.tdf`/`.tsf` are the two formats that travel off Windows well; the rest usually means converting on a Windows machine (or via Wine/Docker) first.

## The question this answers

Two files with the same science inside can need completely different handling depending on the instrument that produced them. A search engine that is perfect for your Thermo data may not open a SCIEX `.wiff` at all. This matrix is the lookup table for "can tool X open file Y, and where can I run it?"

It does **not** rank tools by quality or sensitivity - that belongs in tool-specific comparisons. This is purely about file and platform compatibility.

## Legend

- ✅ Reads the format **natively** (no conversion needed)
- 🔄 **Convert to `mzML` first** (typically with ProteoWizard MSConvert)
- 🟡 **Partial / version- or module-dependent** (see notes)
- — Not supported, or not a typical input
- 💰 Commercial (paid license required)

## Matrix 1 - Native raw-format support

| Tool                   | Thermo `.raw` | Bruker `.d` (timsTOF) | SCIEX `.wiff` | Agilent `.d` | Waters `.raw` | Open `.mzML` |
| ---------------------- | :-----------: | :-------------------: | :-----------: | :----------: | :-----------: | :----------: |
| FragPipe / MSFragger   |      ✅       |         ✅ ^1         |      🔄       |      🔄      |      🔄       |      ✅      |
| DIA-NN                 |      ✅       |          ✅           |     ✅ ^2     |      🔄      |      🔄       |      ✅      |
| MaxQuant               |      ✅       |          ✅           |      ✅       |      ✅      |      🔄       |      ✅      |
| MetaMorpheus           |      ✅       |          🔄           |      🔄       |      🔄      |      🔄       |    ✅ ^3     |
| Sage                   |     🟡 ^4     |         🟡 ^4         |      🔄       |      🔄      |      🔄       |    ✅ ^5     |
| Comet                  |      🔄       |          🔄           |      🔄       |      🔄      |      🔄       |    ✅ ^6     |
| OpenMS                 |     🔄 ^7     |          🔄           |      🔄       |      🔄      |      🔄       |      ✅      |
| AlphaPept / AlphaDIA   |      ✅       |          ✅           |      🔄       |      🔄      |      🔄       |      ✅      |
| Skyline                |      ✅       |          ✅           |      ✅       |      ✅      |      ✅       |    ✅ ^9     |
| Spectronaut 💰         |      ✅       |          ✅           |      ✅       |      —       |      ✅       |    ✅ ^8     |
| Proteome Discoverer 💰 |      ✅       |        🟡 ^10         |      🟡       |      🟡      |      🟡       |      ✅      |
| PEAKS Studio 💰        |      ✅       |          ✅           |      ✅       |      ✅      |      ✅       |    ✅ ^11    |

**Notes**

1. FragPipe reads Bruker `.d` natively for ddaPASEF (timsTOF). Other Bruker `.d` acquisitions should be converted to `mzML`. timsTOF reading on Windows needs the Visual C++ 2017 redistributable installed.
2. DIA-NN reads SCIEX `.wiff` only on **Windows**, and only after copying the ProteoWizard SCIEX/Clearcore `.dll` files into the DIA-NN folder. On native Linux builds DIA-NN supports `.d`, `.raw`, `.mzML`, and its own `.dia` only (no `.wiff`).
3. MetaMorpheus also accepts `.mgf`. `.mzML` must be centroided.
4. Sage began as an `mzML`-only engine; recent versions add direct Thermo `.raw` and Bruker `.d` (`.tdf`) reading. If you are on an older build or hit trouble, fall back to `mzML`.
5. Sage also reads `mzMLb` (HDF5-backed mzML) and can stream compressed spectra from cloud storage.
6. Comet also reads `mzXML`, `.mgf`, and `.ms2`.
7. OpenMS works on `mzML` natively; convert vendor formats with MSConvert or ThermoRawFileParser first. It also ships its own conversion tools.
8. Spectronaut additionally takes its `HTRMS` compressed format and supports dia-PASEF, SWATH, and FAIMS-DIA methods. Documented vendors: Thermo, SCIEX, Bruker, Waters.
9. Skyline reads all major vendor formats natively on **Windows** through the bundled ProteoWizard libraries (Thermo, SCIEX WIFF1/WIFF2, Agilent, Waters, Bruker, Shimadzu), plus `mzML`/`mzXML`.
10. Proteome Discoverer is Thermo-native; other vendors depend on installed nodes/modules and licensing, so treat non-Thermo support as version-dependent.
11. Exact PEAKS vendor and instrument support depends on version and licensed modules; verify against the current PEAKS documentation for your release.

## Matrix 2 - Platforms and interface

| Tool                   | Windows | Linux | macOS | Interface              | License         |
| ---------------------- | :-----: | :---: | :---: | ---------------------- | --------------- |
| FragPipe / MSFragger   |   ✅    |  ✅   |  🟡   | GUI + CLI              | Free (academic) |
| DIA-NN                 |   ✅    |  ✅   |   —   | GUI (Win) + CLI        | Free            |
| MaxQuant               |   ✅    |  ✅   |   —   | GUI (Win) + CLI        | Free            |
| MetaMorpheus           |   ✅    |  ✅   |  ✅   | GUI + CLI              | Open source     |
| Sage                   |   ✅    |  ✅   |  ✅   | CLI                    | Open source     |
| Comet                  |   ✅    |  ✅   |  ✅   | CLI                    | Open source     |
| OpenMS                 |   ✅    |  ✅   |  ✅   | CLI + TOPPView GUI     | Open source     |
| AlphaPept / AlphaDIA   |   ✅    |  ✅   |  ✅   | GUI + CLI              | Open source     |
| Spectronaut 💰         |   ✅    |   —   |   —   | GUI                    | Commercial      |
| Skyline                |   ✅    |  🟡   |   —   | GUI + CLI (SkylineCmd) | Free            |
| Proteome Discoverer 💰 |   ✅    |   —   |   —   | GUI                    | Commercial      |
| PEAKS Studio 💰        |   ✅    |   —   |  🟡   | GUI                    | Commercial      |

- MaxQuant runs as a GUI on Windows and from the command line on Linux (via .NET/Mono).
- FragPipe and MetaMorpheus run on macOS, but native **vendor** reading is most reliable on Windows/Linux; on macOS, plan to work from `mzML`.
- Skyline is a Windows application; Linux/macOS use is typically through containers or remote Windows, not a native build.

## The conversion hub: ProteoWizard / MSConvert

When native support runs out, almost everyone routes through **ProteoWizard MSConvert**. Per ProteoWizard's own documentation, the bundled vendor readers cover:

| Vendor            | Formats MSConvert reads                         |
| ----------------- | ----------------------------------------------- |
| Thermo Scientific | `.raw`                                          |
| Bruker            | Compass `.d`, `YEP`, `BAF`, `FID`, `TDF`, `TSF` |
| SCIEX             | `WIFF` / `WIFF2`                                |
| Agilent           | MassHunter `.d`                                 |
| Waters            | MassLynx `.raw` / UNIFI                         |
| Shimadzu          | `LCD` (except ITOF)                             |
| AB                | `T2D`                                           |

It writes `mzML`, `mzXML`, `MGF`, and (recent versions) `txt`. **The vendor readers require Windows** and Microsoft .NET 4.8 or higher. On Linux/macOS, MSConvert is usually run via the official ProteoWizard Docker image (Wine under the hood).

Practical rule: when in doubt, convert to **centroided `mzML`** with MSConvert and feed that to any tool above.

## Native reading on Linux and macOS

Two vendor formats travel off Windows cleanly, which matters for cluster and cloud pipelines:

- **Thermo `.raw`** can be read on Linux/macOS without Windows through **ThermoRawFileParser** (.NET, cross-platform). This is why tools like MetaMorpheus read Thermo `.raw` directly on Linux, and why Thermo conversion works in Docker.
- **Bruker timsTOF `.tdf`/`.tsf`** are readable on Linux because Bruker's **TDF-SDK** ships Windows _and_ Linux builds. This is what lets DIA-NN, FragPipe, and MaxQuant read Bruker `.d` natively on Linux servers. Note TDF-SDK does **not** read the older `.baf`.

Everything else - SCIEX `.wiff`, Agilent `.d`, Waters `.raw` - depends on **Windows-only** vendor DLLs. On Linux/macOS, convert to `mzML` first (typically on a Windows box or via the ProteoWizard Docker image).

## Quick decision guide

- **"I have Thermo `.raw`"** - open it directly in FragPipe, DIA-NN, MaxQuant, MetaMorpheus, Spectronaut, Skyline, Proteome Discoverer, or PEAKS. For Comet or OpenMS, convert to `mzML` first.
- **"I have Bruker timsTOF `.d`"** - DIA-NN, FragPipe (ddaPASEF), MaxQuant, Spectronaut, Skyline, and PEAKS read it natively; convert other acquisitions to `mzML`.
- **"I have SCIEX `.wiff`"** - MaxQuant, Spectronaut, Skyline, and PEAKS read it natively. DIA-NN reads it on Windows with the SCIEX DLLs. Otherwise convert to `mzML`.
- **"I have Agilent `.d`"** - MaxQuant, Skyline, and PEAKS read it natively; otherwise convert to `mzML`.
- **"I have Waters `.raw`"** - Spectronaut, Skyline, and PEAKS read it natively; otherwise convert to `mzML`.
- **"I work on Linux/macOS with open-source tools"** - standardize on `mzML` and use Comet, Sage, OpenMS, MetaMorpheus, FragPipe, or DIA-NN. Thermo `.raw` and Bruker `.tdf`/`.tsf` also work natively there.

## A note on completeness

This matrix is **not exhaustive**. It covers widely used tools and the most common vendor formats; it omits many specialized, top-down, metabolomics, and instrument-vendor tools. Format support also **changes between versions** - tools add native readers, vendors revise SDKs (for example the SCIEX WIFF converter roadmap), and OS support shifts. Always confirm against the current documentation for the exact tool version you are running before committing a pipeline. If you spot something out of date, please open a PR.

## Caveats

- "Native" here means the tool opens the format without a separate conversion step. It does not promise every acquisition mode (DDA, DIA/PASEF, MS3, ion mobility) is equally supported - check the tool's mode-specific docs.
- Commercial tools (💰) often have the broadest native vendor coverage, but exact support is gated by version and licensed modules.
- Converting to `mzML` is safe and universal, but it can be lossy or bulky for ion-mobility data; for timsTOF, prefer keeping native `.d` when the tool supports it.
- This page focuses on **bottom-up** discovery tools. Targeted (SRM/PRM) and top-down workflows have their own tooling and compatibility quirks.

## Related

- [File Format Cheat Sheet](file-format-cheat-sheet.md) - what each format actually is and how to convert it
- [Beginner's Guide](beginners-guide.md) - how a full analysis fits together
- Main list: [Discovery proteomics](../README.md#discovery-proteomics) | [Identification](../README.md#identification) | [Quantitative proteomics](../README.md#quantitative-proteomics) | [DIA tools](../README.md#dia-tools) | [Targeted / SRM / PRM](../README.md#targeted--srm--prm)

---

_This guide reflects the author's experience as of the last reviewed date. Spot an error or something out of date? Open a [Discussion or update PR](../CONTRIBUTING.md#writing-a-guide) - guides are meant to be refreshed. When experts genuinely disagree and cannot reconcile, we also welcome [competing guides](../GOVERNANCE.md#guide-disagreements)._
