# ProjectOne — Current State
_Updated: 2026-08-30 — session: integrator (post deps-infra merge)_
## Current focus
deps-infra (T-012) merged to `main` (Brewfile + pipx aider + `bin/` wrappers, docs in WARP.md). Worktree/branch cleaned up. diy-track and trip-track continue in parallel; diy-track currently blocked awaiting user input in its own conversation.
## Status snapshot
- T-012 (deps-infra): merged to main (`c49e0db`). Brewfile (gh, librsvg, poppler, python@3.12, pipx); aider migrated to `pipx install -e tools/aider`; `bin/aider` wrapper verified. Conventions documented in WARP.md.
- T-008/T-010 (trip-track): trip params locked (dates flexible, must cover 25 Nov 2026, 1-stop OK); fare search logged in context/flight-tracking.md (best so far ≈£504, above £480 threshold). T-010 Slack design reworked to a portable webhook/bot-token approach (scripts/slack_notify.sh, scripts/slack_pull_feedback.sh) instead of Oz-specific triggers; Scheduled Agent creation deferred pending confirmed paid plan.
- T-007 (diy-track): in progress, currently blocked awaiting user input in its own conversation.
- purpose/tasks tracks already on main from earlier; speech-track still parked unmerged.
## Active worktrees
- `main` — `/Users/linuslin/Desktop/ProjectOne` — integrator checkout.
- `session/trip-taiwan` — `../ProjectOne-trip` — T-008/T-010, active.
- `session/diy-panel` — `../ProjectOne-diy` — T-007, active (blocked on user).
- `session/speech` — `../ProjectOne-speech` — parked, unmerged.
- `session/ai-cost-research` — `../ProjectOne-ai-costs` — original T-011 merged, but branch tip has one unmerged commit (OpenClaw deep-dive); being resumed for a Claude API key + Aider discussion.
- `session/deps-infra` (pipx aider), `session/purpose`, `session/tasks-intake` were merged and pruned (worktrees + local branches removed).
## Open threads
- After live aider (old `.venv`) exits: `rm -rf /Users/linuslin/Desktop/ProjectOne/.venv` on main checkout.
- Other active worktrees need to merge/rebase from main to pick up `bin/` + Brewfile + WARP.md changes.
- T-002/T-003 and speech-track still open as before.
## Next actions
1. Remove deprecated `.venv` when no process holds it.
2. Once ai-cost-research's Claude API key + Aider discussion wraps, merge its OpenClaw deep-dive commit and prune that worktree too.
3. Resume speech-track / profile / privacy when user is ready.
## Settled
- History/versioning via git, not append-only files (see WARP.md).
- Task intake default: single-agent triage; parallel worktrees are an escalation.
- System deps via Brewfile; Python CLIs via pipx; invoke through `bin/` wrappers (see WARP.md Dependency conventions).
