# Wiki Log

Append-only record of wiki operations. Entry format: `## [YYYY-MM-DD] <op> | <title>` — parseable with `grep "^## \[" log.md | tail -5`.

---

## [2026-08-05] restructure | Convert project to explicit Karpathy-style wiki layout

Moved `articles-md/` and the `articles-pdf` symlink under `raw/` (immutable source layer) and `summaries/` under `wiki/` (AI-maintained layer). Updated all path references in `CLAUDE.md`, `README.md`, `professional-summary.md`, `.gitignore`, and the `update-status` skill. Git history preserved through the renames. Commit `b42d313`.

## [2026-08-05] scaffold | Create wiki index, log, and topics directory

Created `wiki/index.md` (content catalog: main page, 19 planned topic pages seeded from `professional-summary.md` §4.1–4.12 and §8.1–8.7, all 68 source summaries listed by tier with one-line descriptions) and this log. Created `wiki/topics/` for the thematic layer, to be populated next.
