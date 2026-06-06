# CLAUDE.md — Professional Summary Project

## Project Purpose

This project processes scientific journal articles (PDFs) authored or co-authored by **Jason A. Milbrandt** (atmospheric scientist, Environment and Climate Change Canada / ECCC) to:

1. Produce an AI-readable `.md` version of each article (to avoid re-processing PDFs in future sessions)
2. Produce a structured summary `.md` file for each article, including a section on impact and citation counts drawn from the internet
3. Aggregate the per-article summaries into a **professional summary** document describing the author's research contributions — intended for use in future AI-assisted research and publication work

## Author Context

- **Jason A. Milbrandt**, Research Scientist at ECCC (Meteorological Research Division)
- Specialty: cloud microphysics parameterization for numerical weather prediction (NWP)
- Primary contribution: development of the **Milbrandt–Yau (MY) multimoment bulk microphysics scheme** and the **Predicted Particle Properties (P3)** scheme, both widely used in mesoscale NWP models (WRF, GEM, CM1, E3SM, etc.)
- Email: jason.a.milbrandt@gmail.com

---

## Folder Structure

```
professional-summary/
├── CLAUDE.md                      ← this file
├── STATUS.md                      ← processing status and paper inventory
├── articles-pdf/                  ← source PDFs (do not modify)
│   ├── 0_PDFs-published/          ← symlink to full published-papers directory
│   └── Author_etal_YYYY.pdf
├── articles-md/                   ← full article in markdown (one per PDF)
│   └── Author_etal_YYYY.md
├── summaries/                     ← structured summary per article
│   └── Author_etal_YYYY-summary.md
├── professional-summary.md        ← aggregated professional summary (built from summaries/)
└── _archive_v1/                   ← prior exploratory work (ignore)
```

---

## Authorship Tiers

All papers are tagged with a tier reflecting Milbrandt's level of intellectual contribution. The tier appears as an `Author's role` field in each summary's metadata block and governs how the paper is represented in `professional-summary.md`.

| Tier | Label | Description |
|------|-------|-------------|
| **Tier 1** | Lead contributor | First author, or co-first where Milbrandt drove the science on equal footing (e.g., P3 Parts I & II). Full intellectual ownership. |
| **Tier 2** | Key co-author | Not first author, but made a substantive intellectual contribution — co-designed the study, provided domain expertise central to the results, or supervised the lead researcher. |
| **Tier 3** | Contributing co-author | Real but supporting contribution — provided data, ran a model, reviewed the manuscript, or contributed to analysis without driving the intellectual direction. |

**Tier assignment rules:**
- First author → Tier 1 (no need to ask)
- Second author → likely Tier 2, but confirm with Jason if ambiguous
- Lower-order author → ask Jason; cannot be inferred from position alone
- Second authorship does not guarantee Tier 2 (e.g., some Gultepe and Korolev papers are Tier 3)

**Effect on `professional-summary.md`:**
- Tier 1 and Tier 2 papers appear in the main per-article contributions narrative
- Tier 3 papers appear in a separate "Related Contributions" section
- Language in summaries should not overstate the focal author's role — use "Milbrandt contributed X" rather than "Milbrandt developed X" for Tier 2/3 unless accurate

**Paper inventory (as of 2026-06-06):** 56 complete (29 Tier 1/2 + 27 Tier 3) + 12 Tier 3 pending = 68 total in scope. See `STATUS.md` for the full list.

---

## File Naming Convention

PDF filenames vary (some include journal abbreviations, some don't). Use a **normalized stem** for all output files regardless of the PDF name:

| Authors | Convention | Example |
|---------|-----------|---------|
| 1–2 authors | `LastName_LastName_YYYY` | `Milbrandt_Yau_2005a` |
| 3+ authors | `LastName_etal_YYYY` | `Milbrandt_etal_2008` |

- Strip journal abbreviations and topic descriptors from PDF names (e.g., `Milbrandt_Morrison_2013-grpl_density.pdf` → stem `Milbrandt_Morrison_2013`)
- Preserve part suffixes where meaningful (e.g., `_2005a`, `_2005b`, `_2006a`, `_2006b`)
- Use first author's last name always

| Source PDF | Markdown | Summary |
|-----------|----------|---------|
| `articles-pdf/Milbrandt_Yau_2005a.pdf` | `articles-md/Milbrandt_Yau_2005a.md` | `summaries/Milbrandt_Yau_2005a-summary.md` |
| `articles-pdf/Milbrandt_Morrison_2013-grpl_density.pdf` | `articles-md/Milbrandt_Morrison_2013.md` | `summaries/Milbrandt_Morrison_2013-summary.md` |
| `articles-pdf/Jouan_Milbrandt_JAS_2019.pdf` | `articles-md/Jouan_Milbrandt_2019.md` | `summaries/Jouan_Milbrandt_2019-summary.md` |
| `articles-pdf/Morrison_etal_2015-P3_part2.pdf` | `articles-md/Morrison_etal_2015b.md` | `summaries/Morrison_etal_2015b-summary.md` |
| `articles-pdf/Milbrandt_Morrison_2016-P3_part3.pdf` | `articles-md/Milbrandt_Morrison_2016.md` | `summaries/Milbrandt_Morrison_2016-summary.md` |
| `articles-pdf/Milbrandt_etal_2016_WAF.pdf` | `articles-md/Milbrandt_etal_2016.md` | `summaries/Milbrandt_etal_2016-summary.md` |

Multi-part papers that form a natural series may be summarized together in a single combined file, but only if the papers are best understood as a unit. Always note this at the top of a combined summary. The combined filename should reflect the series as a whole rather than any individual paper (e.g., `summaries/Milbrandt_Yau_2005ab-summary.md` for the 2-part MY series; `summaries/Morrison_Milbrandt_2015_2016-P3-summary.md` for the 3-part P3 series spanning 2015–2016). Individual per-paper summaries may also exist alongside a combined summary and should include a cross-reference note pointing to the combined file.

---

## Output Formats

### 1. Article Markdown (`markdown/Author_etal_YYYY.md`)

A clean, faithful conversion of the PDF to markdown. Goal: preserve scientific content for future AI use without re-processing the PDF.

- Preserve all section headings, equations (use LaTeX notation inline), tables, and figure captions
- Do not add interpretation or commentary
- Note any figures that could not be rendered as: `[Figure X: <caption text> — image not reproducible in markdown]`
- Include full citation at the top as a header block

### 2. Article Summary (`summaries/Author_etal_YYYY-summary.md`)

A structured interpretive summary. Use the following section template:

```markdown
# Summary: Author et al. (YYYY)

**Full citation:** ...
**Journal:** ...
**Year:** ...
**Authors:** ...
**DOI:** ... (if available)
**Author's role:** Tier [N] — [brief description of Milbrandt's specific contribution]

---

## Overview
[2–4 sentence plain-language description of what the paper does and why it matters]

## Context and Motivation
[Background: why was this work needed? What gap did it fill?]

## Key Scientific Contributions
[Bullet list of the most important contributions/findings]

## Methods Summary
[Brief description of the approach — model, data, experimental design]

## Key Results
[Summary of main results, with key numbers/findings]

## Limitations and Caveats
[What the paper acknowledged as limitations, or known weaknesses]

## Relation to Author's Research Program
[How this paper fits into Milbrandt's broader body of work. For Tier 1: describe
intellectual ownership and the paper's place in the author's arc. For Tier 2: be
specific about what Milbrandt contributed vs. what the lead drove. For Tier 3: note
the contribution and explain why the paper is relevant to the author's work.]

## Impact and Citations
[See guidelines below]
```

#### Impact and Citations Section

- **Citation count**: Query the **Semantic Scholar API** (free, no key required). **Prefer the DOI-based endpoint** — it is faster, unambiguous, and avoids rate-limit errors on the search endpoint:  
  `https://api.semanticscholar.org/graph/v1/paper/DOI:<doi>?fields=title,citationCount,year`  
  Fall back to title search only if the DOI is unavailable:  
  `https://api.semanticscholar.org/graph/v1/paper/search?query=<title>&fields=title,citationCount,year,authors`  
  Use the returned `citationCount` field. Note the retrieval date. If rate-limited (HTTP 429), wait a few seconds and retry sequentially rather than in parallel.
- **Impact narrative**: Based on the citation count, any web-searchable context (follow-on papers, model implementations, comparative studies), describe the paper's influence on the field.
- Format:
  ```markdown
  ## Impact and Citations

  **Citation count:** ~NNN (Semantic Scholar, retrieved YYYY-MM-DD)

  [2–4 sentences on influence: downstream implementations, comparative studies, known limitations addressed by follow-on work, etc.]
  ```

---

## Skills

- **`anthropic-skills:pdf`** (built-in) — used for PDF extraction when converting articles to markdown
- **`build-professional-summary`** *(future)* — will aggregate summary files into `professional-summary.md` once the summary format has stabilized

The PDF→markdown conversion and article summarization workflows are handled inline using the instructions in this file (no custom skill needed).

---

## Structure of `professional-summary.md`

The aggregated professional summary has two main sections reflecting the authorship tiers:

1. **Main narrative (Tier 1 & selected Tier 2)** — Milbrandt's primary research contributions, told chronologically. Tier 2 papers where Milbrandt made a substantive intellectual contribution are included here.
2. **Related Contributions (Tier 2 & 3)** — Papers where Milbrandt was a supporting or contributing co-author. Presented in a separate section to avoid inflating credit. A brief framing paragraph notes that these reflect Milbrandt's role as a domain expert brought in by other research groups, not as the primary intellectual driver.

---

## Workflow

### Processing a new article
1. Confirm the normalized stem (see naming convention above) and the tier (ask Jason if uncertain)
2. Use the built-in `pdf` skill to extract the PDF → clean and save as `articles-md/<stem>.md`
3. Using the markdown file + the summary template, produce `summaries/<stem>-summary.md` (includes Semantic Scholar citation lookup and `Author's role` field)
4. Update `STATUS.md` to mark the paper as complete

### Current processing plan (as of 2026-06-06)
1. ✅ **Phase 1 complete:** All 20 Tier 1/2 lead-authored papers summarized
2. ✅ **Phase 2 complete:** All 9 Tier 2 co-authored papers summarized
3. 🔲 **Phase 3 (next):** Update `professional-summary.md` incorporating Phases 1 & 2
4. 🔲 **Phase 4 (in progress):** Process the 39 Tier 3 co-authored papers — 27 done (Boudala_2021, Boudala_2022, Boudala_Milbrandt_2023, Cholette_2020, Dawson_2016, Fan_2017, Gong_2015, Gultepe_Milbrandt_2007, Gultepe_Milbrandt_2010, Gultepe_etal_2014_BAMS, Han_2019, Huang_2021, Isaac_2012, Jensen_2017, Joe_2020, Joe_2025, Johnson_2019, Kiktev_2017, Korolev_2020, Korolev_Milbrandt_2022, Mailhot_2012, Makar_2015a, Makar_2015b, Makar_2021, McTaggart-Cowan_2019, Mo_2012, Mo_2019), 12 remaining; next: Morrison_etal_2016
5. 🔲 **Phase 5:** Add "Related Contributions" section to `professional-summary.md`

---

## Notes and Conventions

- Always use Semantic Scholar (not Google Scholar) for citation lookups — GS blocks automated queries
- If a paper is not found on Semantic Scholar, note that and try a DOI-based lookup
- Citation counts are approximate and should always include a retrieval date
- Mathematical notation: prefer LaTeX inline (`$...$`) for all equations in markdown files
- The `professional-summary.md` file is the primary deliverable for downstream AI use; treat it as a living document
- Do not modify files in `_archive_v1/` or `articles/`

### Flagging unverified interpretive claims (`⚠ verify`)

Summaries contain two kinds of content: **extracted** facts (drawn directly from the paper's own text) and **interpretive** claims (drawn from background knowledge — e.g., which models adopted a scheme, citation/impact narratives, how a paper relates to the author's other work, attributions of later schemes to specific papers/years). Interpretive claims are the highest-risk for error and have already produced mistakes (e.g., wrongly stating the MY scheme was in CM1/E3SM; mis-dating the P3 series to 2013).

Convention: when writing a summary or the professional summary, **tag any interpretive cross-reference that is not verified against the paper itself or a checked source** with `⚠ verify` inline, e.g.:

> The scheme was later adopted in WRF and CM1 ⚠ verify.

This applies especially to: model-implementation claims, citation/impact narratives, named attributions of follow-on work (author + year), and "Relation to Author's Research Program" cross-links. Remove the tag only after confirming the claim against the source (paper, journal page, or a web/Semantic Scholar lookup). The author (Jason Milbrandt) can also scan for `⚠ verify` to spot-check quickly.
