---
name: update-status
description: >
  End-of-session wrap-up skill for the professional-summary project. Use this skill
  whenever the user types /update-status, or asks to "wrap up the session", "commit
  progress", "update the status", or "what's next". The skill updates CLAUDE.md and
  STATUS.md to reflect work done this session, commits all changes, and gives a clear
  recommendation on whether to continue or start a new session.
---

# update-status skill

This is a wrap-up routine for the professional-summary project. Run it at the end of
any session where papers were processed. It has five steps — do them in order.

---

## Step 1: Read the current project state

Read both files in full before making any changes:
- `STATUS.md` — the paper inventory and per-paper completion flags
- `CLAUDE.md` — the project instructions, including the "Current processing plan" section

Also scan the current conversation to identify which papers were fully processed this
session (both `articles-md` file written AND summary file written).

---

## Step 2: Update STATUS.md

Make the following edits:

- **"Last updated" date**: Set to today's date in YYYY-MM-DD format.
- **Per-paper rows**: For each paper processed this session, update the row in the
  appropriate "Not yet started" table:
  - Move the row to the correct completed section if one exists, OR update the status
    columns in-place — use whichever pattern matches the existing table format.
  - Mark `articles-md` as ✅ and `summary` as ✅.
  - Add the citation count as a note (e.g., `~17 citations`).
- Do **not** change any rows for papers not touched this session.

---

## Step 3: Update CLAUDE.md

Find the "Current processing plan" section (near the bottom of the file). Update:

- The phase status lines — if all papers in a phase are now complete, mark it ✅.
  If a phase is partially done, leave it 🔲 but update the date comment to today.
- The paper count summary line near the top of the Authorship Tiers section
  (e.g., "20 complete + 9 T2 + 39 T3 pending = 68 total") — update the numbers
  to reflect papers newly completed.

Keep all other content unchanged. Do not rewrite or reformat unrelated sections.

---

## Step 4: Commit

Stage and commit the following:
- `articles-md/` — any new markdown files
- `summaries/` — any new summary files
- `STATUS.md`
- `CLAUDE.md`

Write the commit message in this format:
```
Process <N> Tier <X> paper(s): <FirstAuthor_YYYY>[, <FirstAuthor_YYYY>...]

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
```

Example:
```
Process 4 Tier 2 papers: Barszcz_2018, Cholette_2019, Cholette_2023, Cholette_2024

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>
```

Use `git add` on specific paths (not `git add -A`) to avoid accidentally staging
untracked files outside the project scope.

---

## Step 5: Report to the user

Print a concise end-of-session report in this format:

---

### Session summary

**Completed this session** (N papers):
- `Stem_YYYY` — one-line description, ~N citations
- ...

**Remaining in current phase** (Phase N — <phase name>):
- `Stem_YYYY`
- ...

**Overall progress**: N complete / 68 total

**Recommendation**: [Continue in this session] OR [Start a new session]

> [One sentence explaining the recommendation. If recommending a new session, say
> so clearly. Trigger a new-session recommendation when: 4 or more papers were
> processed this session, the conversation feels long or context-compressed, or
> fewer than 2 papers remain in the phase and picking up a new phase would be
> cleaner in fresh context.]

---

Keep the report tight — the user can see the full STATUS.md if they want details.
