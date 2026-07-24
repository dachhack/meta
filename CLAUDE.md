# meta — orchestrator repo

This repo is an **orchestrator**. It contains no product code. Its job is to
track and coordinate the sibling project repos listed in `projects.md`.

## Ground rules for sessions in this repo

1. **Project state lives in the sibling repos, not here.** `projects.md` is a
   directory, not a source of truth. To learn the real state of a project,
   read its `git log` and its `STATUS.md` — never assume from memory or from
   what this repo says.
2. **Where the siblings are.** Locally, projects sit next to this repo
   (`../<name>`). In a Claude Code cloud session they are cloned to
   `/workspace/<name>`. Check both before declaring a repo missing.
3. **Two files per project, two purposes:**
   - `STATUS.md` — the cross-project read. Last-worked date, blockers, next
     3 tasks. This is what standup/status commands consume.
   - `HANDOFF.md` — in-repo WIP notes for whoever works *inside* that repo
     next. Do not treat it as the orchestrator's status source.
4. **Read-only toward siblings.** Do **not** modify, commit to, or push any
   sibling repo from a session in this repo unless the user explicitly asks
   for that specific change. Running `git log` / `git status` / reading files
   is always fine.
5. Keeping `projects.md` current (especially "Last touched") **is** this
   repo's job — `/standup` does it automatically.

## Commands

- `/standup` — full picture: activity table, idle flags, one recommended
  focus for today; updates "Last touched" in `projects.md`.
- `/status` — the table only, read-only.
