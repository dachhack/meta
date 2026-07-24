# /status — quick cross-project table

A lighter, strictly read-only version of `/standup`: the table only. No
recommendation, no flags section, and **no file edits** (do not update
`projects.md`, do not touch sibling repos).

## Steps

1. Read `projects.md`; tracked projects are the table rows (ignore the
   "Not tracked" section).
2. Resolve each path from the `Path` column; if missing, try
   `/workspace/<name>`; if neither exists, mark "not available locally".
3. For each project (read-only):
   - `git -C <path> log -1 --format="%cs %s"` (last commit date + subject)
   - `git -C <path> status --short`
   - Read `<path>/STATUS.md` if present, for blockers.

## Output

One table: Project | Last commit (date + subject) | Days idle | Blockers
(from STATUS.md, or "no STATUS.md"). Append "(dirty tree)" to any project
with uncommitted changes. Nothing else.
