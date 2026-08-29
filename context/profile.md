# ProjectOne — Profile
_Status: DRAFT v1 — intake interview was offered but skipped by the user. This is a
provisional read based on repo signals, not confirmed preference. Revise as real
usage (speech-track, tasks-track) and any future user input come in._
## Purpose (working draft)
A personal agentic workspace for running short, git-backed AI-agent sessions that
carry real work forward — tasks, notes, and domain-specific tracks (e.g. speech,
task management) — without relying on conversation memory between sessions.
## Signals observed so far
- The handover system (`WARP.md`) prioritizes small, current files over
  ever-growing logs, and treats git history as the record of decisions
  (`git log --grep=Why`). This implies a preference for low-maintenance,
  low-clutter state over exhaustive logging.
- Parallel work is already happening across multiple named tracks in one
  session (`session/speech`, `session/tasks-intake` alongside this
  `session/purpose` track), coordinated via worktrees + branches + an
  orchestrator that merges to `main`. This suggests ProjectOne's early
  scope includes at least a "speech" domain and a "tasks" domain, run
  as concurrent agent sessions.
- The user is comfortable delegating structural/process work (scaffolding,
  handover protocol) to an agent and reviewing/merging results, rather than
  writing it by hand.
## Open questions (asked, not yet answered — revisit later)
- What should ProjectOne primarily be? (second brain / task tracker / coding
  sandbox / research base / life admin / all-purpose)
- Typical working style: short frequent check-ins, long deep-work sessions,
  async/batch, or a mix?
- Desired day-to-day feel: lightweight notebook, rigorous trusted system,
  proactive collaborative partner, or low-touch archive?
- Recurring inputs expected: personal to-dos, code/dev projects, research
  notes, journaling, planning/decisions, writing drafts?
- Top priorities: privacy/data minimalism, speed/low friction, thoroughness &
  traceability, simplicity over features, automation/proactivity?
## How this file should be maintained
- Keep it short and current, like `STATE.md` — this is a profile, not a log.
- When speech-track or tasks-track work merges to `main`, re-read this file
  against what actually got built/used, and correct any wrong guesses here
  rather than layering on speculation.
- If the user answers the open questions above (now or later), replace the
  "Open questions" section with settled answers and fold them into Purpose.
