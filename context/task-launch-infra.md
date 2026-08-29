# Task-launch infra (T-010)
## Problem
Today's session needed a manually-assembled orchestrator + 3 child agents in separate worktrees to handle 3 unrelated asks (a build project, a recurring monitor, a meta-feedback item). That's too much ceremony to repeat every time the user hands ProjectOne a batch of things — which they expect to do often, though not everything warrants a scalable build-out.
## Decided (2026-08-29)
- **Default triage: single agent, no worktree.** When the user hands ProjectOne a batch, one agent triages every item and works them as tracked tasks (tier 2 below) in the current session/branch. It only escalates to tier 3 (parallel worktrees + orchestrator) when it judges that's actually warranted — the user does not have to decide this upfront.
- **Notification + feedback channel: Slack, via Warp's native Oz integration.** Tagging/DM-ing `@Oz` triggers a run and posts results back to the thread — this gives us an outbound notification channel (e.g. "found a good flight deal") and doubles as the inbound feedback-injection channel from item 3 (bulletin board), in one piece of infra instead of two. Tradeoff accepted: requires a Warp team on a paid plan (Build/Max/Business) with credits, and is a new habit for the user to check.
## Tiers (match ceremony to size of the ask)
1. **Quick chore** — answerable/doable in the current conversation. No task entry needed; just do it.
2. **Tracked task, single-agent (default)** — gets a `TASKS.md` line + optional `context/<topic>.md`. Worked on incrementally across normal single-agent ProjectOne sessions, no dedicated worktree.
3. **Big parallel project (escalation, not default)** — only when there's enough independent, parallelizable work to justify multiple concurrent agents. Uses the existing worktree-per-track + orchestrator pattern already documented in `WARP.md`'s "Parallel sessions" section.
4. **Recurring/monitoring task** — needs to run on its own schedule, independent of whether the user has a session open (e.g. flight price tracking). Mechanism: an Oz **Scheduled Agent** (cron-based cloud agent) pointed at a ProjectOne environment, running a fixed prompt that reads the relevant `context/*.md` file, checks/updates it, and flags the user (via the Slack channel above) if a threshold is hit. Real Warp platform primitive (see `oz schedule create`), not something we'd have to build ourselves.
## Next steps (setup, not yet done)
1. Confirm/create a Warp team on an eligible plan (Build/Max/Business) with credits.
2. Connect the Slack integration from the Oz web app (oz.warp.dev/integrations) — authorizes Oz into a Slack workspace and GitHub.
3. Create an Oz environment for ProjectOne (repo + any setup commands) so scheduled/triggered agents can access this repo.
4. Once T-008's trip specifics are set, create an Oz Scheduled Agent for the flight-price check, pointed at that environment.
## Open questions still remaining
- Exact tier-3 escalation heuristic (what specifically should make the triaging agent decide to spin up parallel worktrees) — refine with real examples over time rather than defining it abstractly now.
