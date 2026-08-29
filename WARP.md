# ProjectOne — Agent Operating Guide
This file is auto-loaded by every Warp agent session in this directory. Read it first, every time.
## What ProjectOne is
<!-- DRAFT v2 — see context/profile.md; intake interview offered, skipped by user; grounded in real tasks-track signal (T-006–T-010) now, revisit as more tracks land -->
A personal agentic workspace for offloading day-to-day asks — DIY builds, monitoring/price-tracking, writing & presentation drafts, admin — to a single default agent that triages and tracks them as git-backed tasks, escalating to parallel multi-agent sessions only when a batch is genuinely parallelizable. Current phase: define purpose + profile (T-002), decide privacy posture (T-003).
## The map (where things live)
- `STATE.md` — single source of truth for *current* state. Read at start, update at end. Keep it small.
- `TASKS.md` — current open tasks + ownership. Done tasks are removed; git keeps the record.
- `context/` — curated profile + domain files (one file per topic/project, e.g. `context/flight-tracking.md`). `context/profile.md` holds the current (draft) purpose/profile read.
- `INBOX.md` — drop-box for new ideas/feedback on ProjectOne itself; check it at session-start alongside `STATE.md`/`TASKS.md`, triage entries into `TASKS.md`.
- **History lives in git, not files.** Past state, session records, and decisions are recovered with `git log` — not stored in ever-growing files.
## Session-start ritual (always, before acting)
On your first response in a session, run this before anything else — even if the user jumps straight into a task.
1. Read `STATE.md` — current focus + next actions.
2. Run `git log --oneline -12` to see what recent sessions did.
3. Run `git worktree list` to see any active parallel tracks — a worktree can hold real, uncommitted work even with no live conversation attached to it.
4. Check `TASKS.md` for your assigned/unclaimed task.
5. Restate in 2–3 lines where things stand and what you're about to do. Then proceed.
## Session-end ritual (always, before you stop)
1. Update `STATE.md` to reflect reality *now*. Edit in place; keep it short.
2. Update `TASKS.md`: remove finished tasks, add new ones.
3. Commit — the commit message IS the session log (format below), then push.
   Recover history later with `git log`; decisions with `git log --grep=Why`.

Commit message = session log. Body format: `What:` <what changed>  `Why:` <decision/reasoning, if any>  `Next:` <handoff pointer>.
## Task intake (default triage)
When the user hands you a batch of asks: triage everything yourself as a single agent first (quick chores done inline, bigger items become `TASKS.md` entries with a `context/<topic>.md` if useful). Only escalate to "Parallel sessions" below if the batch genuinely has independent, parallelizable work — that's an escalation, not the default. See `context/task-launch-infra.md` for the full tiering rationale, including how recurring/monitoring tasks should use Oz Scheduled Agents instead of waiting for a session to be opened.
## Parallel sessions (multiple agents at once)
- **One branch per session:** `git worktree add ../ProjectOne-<topic> -b session/<topic> main`. Work only in your worktree.
- **Claim your task:** set Owner + `doing` on your task line in `TASKS.md` (on your branch). Never take a task already owned.
- **Integrate via PR/merge to `main`.** The integrator (lead session or user) resolves conflicts and owns `STATE.md`.
- **Minimize shared-file edits** (touch only your own task line) to keep merges clean.
- **Hand off via committed files/branches, not conversation memory.**
## Principles
- Canonical memory is the repo (small current files + git history), not the conversation. Threads are disposable.
- Recovery never depends on reconnecting to a specific agent conversation. Any fresh session picks up a track via its worktree/branch + git state (`git worktree list`, `git log`, `git status`), not by finding the same conversation again. If a conversation is lost, nothing important should be lost with it — that's the point of committing early and often.
- Files stay small and current; git holds history. No append-only logs.
- Recycle: distill signal into STATE.md; let removed detail live in git history.
