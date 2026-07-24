# Tracked Projects

Paths are relative to this repo's parent directory (siblings of `meta/`).
In a Claude Code cloud session, repos live at `/workspace/<name>` instead — commands fall back to that automatically.

| Project | Path | Goal | Phase | Cadence | Last touched |
|---|---|---|---|---|---|
| stathead | ../stathead | Full-stack NFL fantasy research workbench — React app, daily data pipelines, ML models, MCP server — across redraft/dynasty/best-ball; hardening for public launch at stathead.app | 2026 draft-season feature work: SFB16 scoring + cheatsheet tab merged; SFB16 live-draft support in use | Near-daily Jul–Dec; maintenance-only offseason | 2026-07-24 |
| LegendOfZot | ../LegendOfZot | Ship Wizard's Cavern — 50-floor mobile roguelike (claim the Orb of Zot, escape with the loot) — to Google Play as a $0.99 paid app | Playtest-driven UI/visual polish (b493–b520), pivoting to Play Store release track (signing, AAB, Play Console) | Burst-driven: near-daily during a feature arc, multi-week gaps between | 2026-07-24 |
| ffgame | ../ffgame | Drip Fantasy (dripfantasy.com) — live head-to-head FF battles on real NFL play-by-play; enter the 2026 season (Sep 9) with pilot leagues, solo play, and a converting ads funnel | Pre-season pilot hardening + acquisition: solo onboarding (pods, showdowns), drama presentation, Reddit-ads funnel | Near-daily (Sep 9 season launch is the forcing function) | 2026-07-24 |
| pickdynasty | ../pickdynasty | Epic Pick'em (epicpickem.com) — pick'em leagues for every sport: four formats, mixed-sport slates, bar event nights; money tracked, never processed | Feature-complete on staging; production launch checklist (DEPLOYMENT.md) not yet run | Bursts; weekly minimum until production launch | 2026-07-24 |

## Not tracked (deliberately)

- **ffgame-staging** — build/deploy artifact for ffgame, not a project.
- **f3-q-planner** — mature/maintenance; revisit if active work resumes.
- **mmm_example** — portfolio/educational project, dormant.
- **stathead-pdfs** — data pipeline companion to stathead, dormant.
