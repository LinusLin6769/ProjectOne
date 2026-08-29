# ProjectOne — Profile
_Status: DRAFT v2 — intake interview was offered but skipped by the user; this
read is now grounded in real work from tasks-track's first batch (T-006–T-010,
merged to `main`) rather than pure inference. Still provisional — refine again
as speech-track and future batches land._
## Purpose (working draft)
A personal agentic workspace for offloading day-to-day asks — DIY builds,
monitoring/price-tracking, writing & presentation drafts, admin — to a single
default agent that triages and tracks them as git-backed tasks, escalating to
parallel multi-agent sessions only when a batch is genuinely parallelizable.
## Signals observed so far
- **Real task variety from the first batch** (tasks-track, T-006–T-010): a DIY
  wall display panel (hardware build: InkyPi/Raspberry Pi + e-ink HAT), a
  flight-price advisor (recurring monitoring with a "good deal" heuristic), and
  a feedback/inbox loop for ProjectOne itself. Alongside this, speech-track is
  producing presentation content (an alumni bio slide). Together these show
  ProjectOne's scope is genuinely broad/personal-life, not code-only — hardware
  projects, monitoring/alerts, writing, and admin all count as normal input.
- **Batching is the normal mode, not the exception.** The user handed over 3
  unrelated asks in one go (build project, recurring monitor, meta-feedback
  item), and `context/task-launch-infra.md` explicitly expects this to keep
  happening. The system's job is to absorb a grab-bag, not expect one
  clean request at a time.
- **Default is single-agent triage; parallelism is an escalation.** T-010
  decided: one agent triages a batch and works items as tracked tasks in the
  current session — no worktree — unless the batch has genuinely independent,
  parallelizable work. (The 3-way parallel split happening right now, across
  speech/purpose/tasks tracks, is itself the escalation case, not the norm —
  triggered by this being the first-ever batch needing simultaneous scoping.)
- **Recurring/monitoring work is offloaded to infrastructure, not sessions.**
  Things like flight-price checks are meant to run via Oz Scheduled Agents
  rather than waiting for the user to open a session — the user wants
  ProjectOne to work on their behalf between sessions, not just during them.
- **Notification + feedback loop: Slack**, via Warp's native Oz integration —
  chosen as one piece of infra for both outbound alerts (e.g. a good flight
  deal) and inbound feedback (the bulletin-board pattern in `INBOX.md`).
- The handover system (`WARP.md`) prioritizes small, current files over
  ever-growing logs, and treats git history as the record of decisions
  (`git log --grep=Why`) — a preference for low-maintenance, low-clutter state
  over exhaustive logging, now reinforced by T-010's tiering (match ceremony
  to size of the ask; don't over-build for small items).
## Open questions (not yet answered directly by the user — revisit later)
- Desired day-to-day feel: lightweight notebook, rigorous trusted system,
  proactive collaborative partner, or low-touch archive?
- Top priorities when these trade off: privacy/data minimalism, speed/low
  friction, thoroughness & traceability, simplicity over features,
  automation/proactivity?
- Privacy posture (T-003, still open): what personal data is in-scope for this
  repo (e.g. trip details, home hardware, personal bio content) vs. out?
- Working-style cadence: is batching-everything-at-once (as seen so far) the
  typical pattern, or will quieter single-item sessions dominate day-to-day?
## How this file should be maintained
- Keep it short and current, like `STATE.md` — this is a profile, not a log.
- When another track's work merges to `main`, re-read this file against what
  actually got built/used, and correct any wrong guesses here rather than
  layering on speculation.
- If the user answers the open questions above (now or later), replace the
  "Open questions" section with settled answers and fold them into Purpose.
