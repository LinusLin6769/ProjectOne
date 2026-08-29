# Task-launch infra (T-010) — DRAFT PROPOSAL, not yet decided
## Problem
Today's session needed a manually-assembled orchestrator + 3 child agents in separate worktrees to handle 3 unrelated asks (a build project, a recurring monitor, a meta-feedback item). That's too much ceremony to repeat every time the user hands ProjectOne a batch of things — which they expect to do often.
## Proposed tiers (match ceremony to size of the ask)
1. **Quick chore** — answerable/doable in the current conversation. No task entry needed; just do it.
2. **Tracked task, single-agent** — gets a `TASKS.md` line + optional `context/<topic>.md`. Worked on incrementally across normal single-agent ProjectOne sessions, no dedicated worktree. This should be the *default* for most incoming items (e.g. today's display-panel research and flight-tracking scoping could have been done this way without a dedicated worktree/branch).
3. **Big parallel project** — only when there's enough independent, parallelizable work to justify multiple concurrent agents. Uses the existing worktree-per-track + orchestrator pattern already documented in `WARP.md`'s "Parallel sessions" section. Reserved for rarer, larger batches — not the default.
4. **Recurring/monitoring task** — needs to run on its own schedule, independent of whether the user has a session open (e.g. flight price tracking). Proposed mechanism: an Oz **Scheduled Agent** (cron-based cloud agent) pointed at a ProjectOne environment, running a fixed prompt that reads the relevant `context/*.md` file, checks/updates it, and flags the user if a threshold is hit. This is a real Warp platform primitive (see `oz schedule create`), not something we'd have to build ourselves.
## Open questions for the user
- Notification: when a scheduled check finds something worth acting on (e.g. a good flight deal), how should the user be told? Options include a Slack/Linear integration ping, or just surfacing it prominently the next time they open a ProjectOne session (e.g. top of `STATE.md`/`INBOX.md`).
- Does the tiered model above match expectations, especially: what should trigger tier 3 (multi-agent/worktree) instead of defaulting to tier 2 (single-agent, tracked)?
- Who decides the tier for an incoming ask — the user up front, or should the agent triage it (and only ask when it's ambiguous)?
