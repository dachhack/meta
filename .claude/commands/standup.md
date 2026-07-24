# /standup — cross-project standup

Produce a standup report across every tracked project, then update
`projects.md`.

## Steps

1. Read `projects.md` in this repo. The tracked projects are the rows of the
   table (ignore the "Not tracked" section).
2. Resolve each project's path: use the `Path` column (e.g. `../stathead`);
   if that directory doesn't exist, try `/workspace/<name>` (cloud sessions).
   If neither exists, report the project as "not available locally" — do not
   guess its state.
3. For each tracked project, gather (read-only — never modify sibling repos):
   - `git -C <path> log --oneline --since="14 days ago"`
   - `git -C <path> status --short` (uncommitted work is a signal worth
     surfacing)
   - `git -C <path> log -1 --format=%cs` (date of last commit)
   - Read `<path>/STATUS.md` if present, for blockers and next tasks. If it
     is missing, note that — don't substitute HANDOFF.md, which is in-repo
     WIP, not orchestrator status.
4. Compute days idle = today − last commit date.

## Output

1. **Table**: Project | Last commit (date + subject) | Days idle | Blockers
   (from STATUS.md, or "no STATUS.md"). Note any dirty working tree.
2. **Stale flags**: call out every project idle **more than 7 days**, with
   its cadence for contrast (e.g. "daily cadence, 9 days idle").
3. **Recommended focus for today** — exactly one project, chosen by weighing
   cadence against staleness: the project furthest behind *its own* cadence
   wins; break ties toward the one with a concrete unblocked "next task" in
   STATUS.md. One or two sentences on why, plus the first task to pick up.

## Update projects.md

Rewrite the "Last touched" column in `projects.md` with each project's actual
last commit date found above. This file edit (inside this repo) is the only
write this command performs.
