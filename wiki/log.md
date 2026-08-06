# Wiki Log

Append-only record of wiki operations. Entry format: `## [YYYY-MM-DD] <op> | <title>` — parseable with `grep "^## \[" log.md | tail -5`.

---

## [2026-08-05] restructure | Convert project to explicit Karpathy-style wiki layout

Moved `articles-md/` and the `articles-pdf` symlink under `raw/` (immutable source layer) and `summaries/` under `wiki/` (AI-maintained layer). Updated all path references in `CLAUDE.md`, `README.md`, `professional-summary.md`, `.gitignore`, and the `update-status` skill. Git history preserved through the renames. Commit `b42d313`.

## [2026-08-05] scaffold | Create wiki index, log, and topics directory

Created `wiki/index.md` (content catalog: main page, 19 planned topic pages seeded from `professional-summary.md` §4.1–4.12 and §8.1–8.7, all 68 source summaries listed by tier with one-line descriptions) and this log. Created `wiki/topics/` for the thematic layer, to be populated next.

## [2026-08-05] topic-pages | First three topic pages (review samples)

Created `topics/p3-scheme.md`, `topics/ice-phase-modernization.md`, and `topics/sip-hiwc-mixed-phase.md` as review samples before batching the remaining 16 themes. Index updated to mark them built. Awaiting Jason's review of depth, tone, and link density.

## [2026-08-05] topic-pages | Remaining 16 topic pages (batch)

Built the remaining 10 Tier 1/2 and 6 Tier 3 topic pages, completing the 19-page seed set from professional-summary.md sections 4.1-4.12 and 8.1-8.7. Added a `*Topic page: [[...]]*` pointer under each corresponding section heading in professional-summary.md. Cleared all `(planned)` markers from wiki/index.md now that every listed topic page exists.

## [2026-08-05] retrofit | Related-topics footers added to all 68 summaries

Appended a `## Related topics` footer with `[[wiki-links]]` to every summary file, inverting the topic-to-source mapping built while writing the 19 topic pages. Verified zero unresolved `[[links]]` across the repo (166 files).

## [2026-08-05] schema | CLAUDE.md schema formalized; STATUS.md conversion note

Added the topic-page format, `[[wiki-link]]` conventions, and the ingest/query/lint workflow (with the read-discuss-write human checkpoint) to CLAUDE.md. Removed the stale "future build-professional-summary skill" note. Added a dated conversion summary to STATUS.md. Ran full verification: link integrity, summary/topic-page coverage, no stale bare paths, git history preserved through the raw/wiki rename. Conversion to an explicit Karpathy-style wiki is complete.

## [2026-08-06] tooling | Repo root made an Obsidian vault for GUI browsing

Made the wiki navigable in a GUI: added tracked `.obsidian/` config (`app.json`, `appearance.json`, `core-plugins.json`, `graph.json`) so opening the repo root as an Obsidian vault gives clickable `[[links]]`, MathJax, backlinks, search, and a colour-grouped graph with no build step. `app.json` excludes `raw/`, `_archive_v1/`, and `.claude/` from the vault; `workspace.json` and caches are gitignored. Vault root must stay at the repo root so `[[professional-summary]]` resolves.

Two render bugs fixed as pre-flight: three unescaped currency `$` (`CAD $800 million` in `applied-mesoscale-nwp` and `Milbrandt_Yau_2001-summary`, `$2.5 billion` in `Taylor_etal_2011-summary`) that MathJax would have paired with the next real delimiter, swallowing prose into equations; and three un-backticked prose mentions of link syntax in this log that would have become phantom graph nodes. Verified after: 90 files in vault scope, 481 wikilinks, zero unresolved, all `$` balanced.
