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
├── .obsidian/                     ← Obsidian vault config (tracked — see below)
├── STATUS.md                      ← processing status and paper inventory
├── professional-summary.md        ← aggregated synthesis (the wiki's main page)
├── raw/                           ← immutable source layer — never modify
│   ├── articles-pdf               ← symlink to published-PDFs directory (gitignored)
│   └── articles-md/               ← full article in markdown (one per PDF)
│       └── Author_etal_YYYY.md
├── wiki/                          ← AI-maintained knowledge layer
│   ├── index.md                   ← content catalog of all wiki pages
│   ├── log.md                     ← append-only operations log
│   ├── topics/                    ← thematic topic pages with [[wiki-links]]
│   └── summaries/                 ← structured summary per article
│       └── Author_etal_YYYY-summary.md
└── _archive_v1/                   ← prior exploratory work (ignore)
```

### Reading the wiki in a GUI (Obsidian)

**The repo root is an Obsidian vault** (added 2026-08-06). Opening
`~/Dropbox/projects/professional-summary` as a vault renders every page with clickable
`[[wiki-links]]`, MathJax equations, backlinks, full-text search, and a graph view — no
build step, since Obsidian reads the markdown in place. The wiki already uses Obsidian's
native conventions exactly (basename-only links, `$...$` math, no frontmatter).

- The vault root **must** stay at the repo root, not `wiki/` — `professional-summary.md`
  lives at the root and is a link target from `wiki/index.md`.
- `.obsidian/app.json` excludes `raw/`, `_archive_v1/`, and `.claude/` from search, Quick
  Switcher, and the graph, so the vault shows only the wiki layer plus the synthesis.
- `.obsidian/` config (`app.json`, `appearance.json`, `core-plugins.json`, `graph.json`) is
  **tracked**; `workspace.json` and caches are gitignored. Don't delete `.obsidian/` as
  cleanup — it is the GUI setup.
- Consequence for editing: an unescaped `$` in prose (e.g. `CAD $800 million`) can pair with
  a later math delimiter and swallow text into an equation. Write currency as `\$`.

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

**Paper inventory (as of 2026-06-06):** 68 complete (30 Tier 1/2 + 38 Tier 3) = 68 total in scope. All papers processed. See `STATUS.md` for the full list.

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
| `raw/articles-pdf/Milbrandt_Yau_2005a.pdf` | `raw/articles-md/Milbrandt_Yau_2005a.md` | `wiki/summaries/Milbrandt_Yau_2005a-summary.md` |
| `raw/articles-pdf/Milbrandt_Morrison_2013-grpl_density.pdf` | `raw/articles-md/Milbrandt_Morrison_2013.md` | `wiki/summaries/Milbrandt_Morrison_2013-summary.md` |
| `raw/articles-pdf/Jouan_Milbrandt_JAS_2019.pdf` | `raw/articles-md/Jouan_Milbrandt_2019.md` | `wiki/summaries/Jouan_Milbrandt_2019-summary.md` |
| `raw/articles-pdf/Morrison_etal_2015-P3_part2.pdf` | `raw/articles-md/Morrison_etal_2015b.md` | `wiki/summaries/Morrison_etal_2015b-summary.md` |
| `raw/articles-pdf/Milbrandt_Morrison_2016-P3_part3.pdf` | `raw/articles-md/Milbrandt_Morrison_2016.md` | `wiki/summaries/Milbrandt_Morrison_2016-summary.md` |
| `raw/articles-pdf/Milbrandt_etal_2016_WAF.pdf` | `raw/articles-md/Milbrandt_etal_2016.md` | `wiki/summaries/Milbrandt_etal_2016-summary.md` |

Multi-part papers that form a natural series may be summarized together in a single combined file, but only if the papers are best understood as a unit. Always note this at the top of a combined summary. The combined filename should reflect the series as a whole rather than any individual paper (e.g., `wiki/summaries/Milbrandt_Yau_2005ab-summary.md` for the 2-part MY series; `wiki/summaries/Morrison_Milbrandt_2015_2016-P3-summary.md` for the 3-part P3 series spanning 2015–2016). Individual per-paper summaries may also exist alongside a combined summary and should include a cross-reference note pointing to the combined file.

---

## Output Formats

### 1. Article Markdown (`raw/articles-md/Author_etal_YYYY.md`)

A clean, faithful conversion of the PDF to markdown. Goal: preserve scientific content for future AI use without re-processing the PDF.

- Preserve all section headings, equations (use LaTeX notation inline), tables, and figure captions
- Do not add interpretation or commentary
- Note any figures that could not be rendered as: `[Figure X: <caption text> — image not reproducible in markdown]`
- Include full citation at the top as a header block

### 2. Article Summary (`wiki/summaries/Author_etal_YYYY-summary.md`)

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

### 3. Topic Page (`wiki/topics/<topic-name>.md`)

A synthesizing page covering one theme across multiple source summaries — not a per-paper page. Filenames are lowercase-hyphenated (e.g. `p3-scheme.md`), not tied to any single paper's stem. Use this template:

```markdown
# Page Title

**Summary:** One to two sentences describing what this page covers.

**Sources:** [[stem1-summary]], [[stem2-summary]], ...

**Last updated:** YYYY-MM-DD

---

Main content: prose organized by theme or chronology, not just a bullet
restatement of each source. Synthesize — connect findings across papers,
note where one paper's result motivates or gets fixed by another, follow
$...$ LaTeX and ⚠ verify conventions as in summaries.

## Related pages

- [[sibling-topic-1]] — why it's related
- [[sibling-topic-2]] — why it's related
```

A topic page should read as connective tissue between summaries, not a duplicate of `professional-summary.md`'s existing prose — pull the summaries' data forward, but articulate the cross-paper narrative in its own words.

---

## Wiki-Links and the Link Graph

`[[wiki-links]]` (double-bracket, page basename without `.md`) are the only cross-reference mechanism in this wiki. Bare filenames in prose (the old convention) are deprecated — always use `[[link]]` syntax so the graph is machine-resolvable.

- **Topic pages link down** to every summary in their `Sources:` line, and **across** to sibling topic pages in `## Related pages`.
- **Summaries link up** via a mechanical `## Related topics` footer — one `[[topic-page]]` entry per topic page that cites this summary. When creating a new summary that a topic page will cite, add the reciprocal footer entry to the summary in the same pass (don't leave it for a later retrofit).
- **`professional-summary.md`** points down to its matching topic page with a one-line `*Topic page: [[...]]*` immediately under each `4.x`/`8.x` section heading.
- Check link integrity periodically: every `[[target]]` should resolve to an existing file basename somewhere in the repo (a lint check — see Lint below).

---

## Skills

- **`anthropic-skills:pdf`** (built-in) — used for PDF extraction when converting articles to markdown

The PDF→markdown conversion, article summarization, topic-page maintenance, and lint workflows are all handled inline using the instructions in this file (no custom skill needed yet — a dedicated `wiki-lint` skill may be worth building once the lint pass is run a few times).

---

## Structure of `professional-summary.md`

The aggregated professional summary has two main sections reflecting the authorship tiers:

1. **Main narrative (Tier 1 & selected Tier 2)** — Milbrandt's primary research contributions, told chronologically. Tier 2 papers where Milbrandt made a substantive intellectual contribution are included here.
2. **Related Contributions (Tier 2 & 3)** — Papers where Milbrandt was a supporting or contributing co-author. Presented in a separate section to avoid inflating credit. A brief framing paragraph notes that these reflect Milbrandt's role as a domain expert brought in by other research groups, not as the primary intellectual driver.

Each `4.x` and `8.x` subsection carries a `*Topic page: [[...]]*` pointer to its corresponding page in `wiki/topics/` — the monolith stays as the narrative spine; the topic page is where the cross-paper synthesis lives and grows.

---

## Workflow

### Ingesting a new article

Follow this order — don't skip the discussion step. Read → discuss → write is what keeps the wiki a synthesis rather than a pile of independently-generated pages.

1. Confirm the normalized stem (see naming convention above) and the tier (ask Jason if uncertain).
2. Use the built-in `pdf` skill to extract the PDF → clean and save as `raw/articles-md/<stem>.md`.
3. Read the article and **discuss key takeaways with Jason before writing anything** — what's the contribution, how does it relate to existing pages, does it change any earlier claim.
4. Produce `wiki/summaries/<stem>-summary.md` using the summary template (Semantic Scholar citation lookup, `Author's role` field).
5. Update or create the relevant `wiki/topics/*.md` page(s) this paper touches — a new paper doesn't just get a summary, it should update whichever topic pages its findings bear on. Add the reciprocal `## Related topics` link in the new summary.
6. Update `wiki/index.md` (new summary + any new/changed topic page) and append an entry to `wiki/log.md`.
7. Update `STATUS.md` to mark the paper as complete.

A single new article may touch several existing topic pages — that's expected and is the point of the wiki pattern (see `notes-LLM_wiki/` at the `my_wiki` project root for the source material this schema follows).

### Answering a question

1. Read `wiki/index.md` first to find relevant topic pages and summaries.
2. Read those pages and synthesize an answer, citing specific `[[pages]]`.
3. If the answer isn't in the wiki, say so — don't guess from general knowledge and present it as sourced.
4. If the answer is valuable and durable, offer to file it back as a new or updated topic page — never into `raw/`, which stays strictly external source material.

### Lint

When asked to lint or audit the wiki, check for: contradictions between pages; orphan pages with no inbound `[[link]]`; broken `[[links]]` that don't resolve to any file; concepts mentioned repeatedly but lacking their own topic page; summaries missing a `## Related topics` footer; and claims flagged `⚠ verify` that are old enough to resolve. There is no dedicated lint skill yet — run this as an ad hoc pass when asked, staggered rather than scheduled, since a full pass over 68+ summaries and 19+ topic pages has a real time/token cost.

### Current processing plan (as of 2026-06-06)
1. ✅ **Phase 1 complete:** All 20 Tier 1/2 lead-authored papers summarized
2. ✅ **Phase 2 complete:** All 9 Tier 2 co-authored papers summarized
3. ✅ **Phase 3 complete (2026-06-06):** `professional-summary.md` fully updated — Tier 1/2 narrative extended through 2025
4. ✅ **Phase 4 complete:** All 38 Tier 3 co-authored papers summarized (Theriault_etal_2015 reclassified to Tier 2, confirmed 2026-06-06)
5. ✅ **Phase 5 complete (2026-06-06):** "Related Contributions" section added to `professional-summary.md` — all 38 Tier 3 papers grouped thematically

---

## Notes and Conventions

- Always use Semantic Scholar (not Google Scholar) for citation lookups — GS blocks automated queries
- If a paper is not found on Semantic Scholar, note that and try a DOI-based lookup
- Citation counts are approximate and should always include a retrieval date
- Mathematical notation: prefer LaTeX inline (`$...$`) for all equations in markdown files
- The `professional-summary.md` file is the primary deliverable for downstream AI use; treat it as a living document
- Do not modify anything under `raw/` or `_archive_v1/`

### Flagging unverified interpretive claims (`⚠ verify`)

Summaries contain two kinds of content: **extracted** facts (drawn directly from the paper's own text) and **interpretive** claims (drawn from background knowledge — e.g., which models adopted a scheme, citation/impact narratives, how a paper relates to the author's other work, attributions of later schemes to specific papers/years). Interpretive claims are the highest-risk for error and have already produced mistakes (e.g., wrongly stating the MY scheme was in CM1/E3SM; mis-dating the P3 series to 2013).

Convention: when writing a summary or the professional summary, **tag any interpretive cross-reference that is not verified against the paper itself or a checked source** with `⚠ verify` inline, e.g.:

> The scheme was later adopted in WRF and CM1 ⚠ verify.

This applies especially to: model-implementation claims, citation/impact narratives, named attributions of follow-on work (author + year), and "Relation to Author's Research Program" cross-links. Remove the tag only after confirming the claim against the source (paper, journal page, or a web/Semantic Scholar lookup). The author (Jason Milbrandt) can also scan for `⚠ verify` to spot-check quickly.
