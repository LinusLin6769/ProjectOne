# ProjectOne — Agent Operating Guide
This file is auto-loaded by every Warp agent session in this directory. Read it first, every time.
## What ProjectOne is
<!-- one-liner; fill in after the intake interview -->
A personal agentic workspace for <TODO: purpose>. Current phase: stand up a reliable session-handover system.
## The map (where things live)
- `STATE.md` — single source of truth for *current* state. Read at start, update at end. Keep it small.
- `TASKS.md` — current open tasks + ownership. Done tasks are removed; git keeps the record.
- `context/` — curated profile + domain files (one file per topic/project, e.g. `context/flight-tracking.md`).
- `INBOX.md` — drop-box for new ideas/feedback on ProjectOne itself; check it at session-start alongside `STATE.md`/`TASKS.md`, triage entries into `TASKS.md`.
- **History lives in git, not files.** Past state, session records, and decisions are recovered with `git log` — not stored in ever-growing files.
## Session-start ritual (always, before acting)
On your first response in a session, run this before anything else — even if the user jumps straight into a task.
1. Read `STATE.md` — current focus + next actions.
2. Run `git log --oneline -12` to see what recent sessions did.
3. Check `TASKS.md` for your assigned/unclaimed task.
4. Restate in 2–3 lines where things stand and what you're about to do. Then proceed.
## Session-end ritual (always, before you stop)
1. Update `STATE.md` to reflect reality *now*. Edit in place; keep it short.
2. Update `TASKS.md`: remove finished tasks, add new ones.
3. Commit — the commit message IS the session log (format below), then push.
   Recover history later with `git log`; decisions with `git log --grep=Why`.

Commit message = session log. Body format: `What:` <what changed>  `Why:` <decision/reasoning, if any>  `Next:` <handoff pointer>.
## Parallel sessions (multiple agents at once)
- **One branch per session:** `git worktree add ../ProjectOne-<topic> -b session/<topic> main`. Work only in your worktree.
- **Claim your task:** set Owner + `doing` on your task line in `TASKS.md` (on your branch). Never take a task already owned.
- **Integrate via PR/merge to `main`.** The integrator (lead session or user) resolves conflicts and owns `STATE.md`.
- **Minimize shared-file edits** (touch only your own task line) to keep merges clean.
- **Hand off via committed files/branches, not conversation memory.**
## Principles
- Canonical memory is the repo (small current files + git history), not the conversation. Threads are disposable.
- Files stay small and current; git holds history. No append-only logs.
- Recycle: distill signal into STATE.md; let removed detail live in git history.
