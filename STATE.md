# ProjectOne — Current State
_Updated: 2026-08-29 — session: parallel-tracks (speech/purpose/tasks)_
## Current focus
First real test of WARP.md's parallel-session model, largely complete: tasks-track and purpose-track are merged into `main`. speech-track has converged (alumni bio-card slide) but is parked — user is revisiting it later, not blocking on it.
## Status snapshot
- purpose-track merged: draft v2 purpose line in `WARP.md` + `context/profile.md`, grounded in this session's real task variety (still flagged DRAFT, pending direct answers to remaining open questions).
- tasks-track merged: T-006 intake done; T-007 (wall display) scoped and parked per user (no further action); T-008 (flight tracker) scoped with TPE locked in as the Taipei airport, date flexibility/stop tolerance still open; T-009 (`INBOX.md` feedback loop) built, unused so far; T-010 (task-launch infra) decided in principle but user wants it to stay a documented plan for now — no Oz Scheduled Agents/Slack setup.
- speech-track (not yet merged, branch `session/speech`, worktree `../ProjectOne-speech`): converged on a 1-slide alumni bio card (real bio + institution-themed design), user fine-tuning directly — parked until user revisits.
## Active worktrees
- `main` — `/Users/linuslin/Desktop/ProjectOne` — integrator's checkout, up to date.
- `session/purpose` — `../ProjectOne-purpose` — merged into main (e4e2fc2); clean; kept in case profile needs further refinement, otherwise removable.
- `session/tasks-intake` — `../ProjectOne-tasks` — merged into main (7f8e13b); clean; kept in case T-007/T-008 need more work, otherwise removable.
- `session/speech` — `../ProjectOne-speech` — NOT merged (bc96015); clean; active/parked at user's request — resume here directly to continue.
Always re-run `git status` in a worktree before trusting this list; it can drift between updates.
## Open threads
- T-002 (purpose/profile): DRAFT v2, could still be refined if user answers the remaining profile questions (day-to-day feel, priorities, cadence).
- T-003 (privacy posture): still fully open, untouched this session.
- T-004/T-005 (pilot slice / battle-test parallel flow): this batch (3 worktrees, 2 merges, 1 conflict resolved) is a real instance of both — worth explicitly closing once speech-track also lands.
- T-007/T-008: paused pending user decisions (T-007: budget/screen/enclosure; T-008: date flexibility, stop tolerance).
## Next actions
1. Merge speech-track whenever the user resumes/finishes fine-tuning it.
2. Close out T-004/T-005 once speech-track lands (all 3 tracks integrated).
3. Otherwise idle — remaining open items need user decisions, not agent action.
## Settled
- History/versioning via git, not append-only files (see WARP.md).
- Task intake default: single-agent triage by default; parallel worktrees are an escalation, not the default (see WARP.md's "Task intake" section).
