# Professional Summary — Jason A. Milbrandt

A structured library of Jason Milbrandt's published scientific work, built for AI-assisted research and writing tasks.

## What this is

This repository contains AI-readable versions of 68 peer-reviewed papers authored or co-authored by Jason A. Milbrandt (Research Scientist, Environment and Climate Change Canada), along with structured per-paper summaries and an aggregated professional summary document. The primary use case is providing an AI assistant (Claude Code) with accurate, well-framed context about the author's research program when drafting new papers, grant text, cover letters, or other scientific writing.

## Repository structure

```
professional-summary/
├── README.md                      ← this file
├── CLAUDE.md                      ← instructions for the AI assistant
├── STATUS.md                      ← paper inventory and processing status
├── professional-summary.md        ← aggregated synthesis of all 68 papers
├── summaries/                     ← one structured summary per paper (68 files)
│   └── Author_etal_YYYY-summary.md
├── articles-md/                   ← full article text in markdown (one per PDF)
│   └── Author_etal_YYYY.md
└── articles-pdf/                  ← source PDFs (not committed to git)
```

## Key files

**`professional-summary.md`** is the primary reference document. It synthesizes all 68 papers into a single narrative organized by authorship tier and research theme, and is the intended entry point for any AI session involving Milbrandt's publication record. It includes a coverage tracker and pointers to individual summary files.

**`summaries/`** contains one structured summary per paper. Each file follows a standard template: full citation, author's role, overview, context and motivation, key scientific contributions, methods, results, limitations, relation to the author's research program, and citation count (from Semantic Scholar).

**`articles-md/`** contains the full text of each article converted from PDF to markdown, preserving equations, tables, and figure captions. These exist so that detailed technical content can be retrieved without re-processing the source PDFs.

**`STATUS.md`** is the processing inventory: it tracks which papers have been converted to markdown and summarized, records citation counts, and documents the file-naming conventions and any duplicate-PDF resolutions.

## Authorship tiers

Papers are classified by Milbrandt's level of intellectual contribution:

| Tier | Label | Description |
|------|-------|-------------|
| **Tier 1** | Lead contributor | First author, or co-first where Milbrandt drove the science on equal footing |
| **Tier 2** | Key co-author | Substantive intellectual contribution — co-designed the study, supervised the lead, or provided domain expertise central to the results |
| **Tier 3** | Contributing co-author | Supporting role — provided a model/scheme, ran simulations, reviewed the manuscript |

The tier system exists to keep attributions of intellectual ownership accurate in AI-generated text.

## Research scope

The 68 papers span 2001–2025 and cover:

- The **Milbrandt–Yau (MY) multimoment bulk microphysics scheme** (2005–2006, four-part series) — Milbrandt's foundational contribution, operational in ECCC's HRDPS and the WRF community model
- **Observational validation and theoretical consolidation** of the MY scheme (2008–2010)
- **Ice-phase modernization**: snow-category updates, prognostic graupel density (2012–2013)
- The **Predicted Particle Properties (P3) scheme** (2015–2016, three-part series) — a property-predicting replacement for fixed ice categories, operational at ECCC
- **Modern P3 extensions**: triple-moment ice, predicted liquid fraction, multiple free categories, explicit surface precipitation-type prediction (2019–2025)
- **Operational NWP**: the pan-Canadian 2.5-km HRDPS system description (2016) and scale-adaptation of P3 for global models
- **Related contributions** (Tier 3): 38 papers where Milbrandt provided his schemes or expertise to other groups' studies — scheme intercomparisons, GEM-MACH air quality, Olympic forecast systems, fog/visibility, and more

## Notes

- Source PDFs are not committed to this repository.
- Citation counts are from the Semantic Scholar API and are approximate; retrieval dates are noted in each summary.
- Interpretive claims not directly verified against a paper's text are tagged `⚠ verify` in the summary files.
- `CLAUDE.md` contains detailed instructions for the AI assistant, including the summary template format, file-naming conventions, and the workflow for processing new papers.
