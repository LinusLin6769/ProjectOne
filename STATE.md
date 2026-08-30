# ProjectOne — Current State
_Updated: 2026-08-30 — session: deps-infra (T-012)_
## Current focus
deps-track built dependency management infra on `session/deps-infra` (Brewfile + pipx aider + `bin/` wrappers). Awaiting integrator merge to `main`. Old shared `.venv` is deprecated but still held open by a live aider process — remove later when safe.
## Status snapshot
- T-012 (deps-infra): Brewfile (gh, librsvg, poppler, python@3.12, pipx); aider migrated to `pipx install -e tools/aider`; `bin/aider` wrapper verified (`./bin/aider --version` → 0.86.3.dev53+g5dc9490bb). Conventions documented in WARP.md.
- purpose/tasks tracks already on main from earlier; speech-track still parked unmerged.
## Active worktrees
- `main` — `/Users/linuslin/Desktop/ProjectOne` — integrator checkout.
- `session/deps-infra` — `../ProjectOne-deps` — THIS track; ready to merge (do not self-merge).
- `session/speech` — `../ProjectOne-speech` — parked, unmerged.
- Other session worktrees may still exist; re-run `git worktree list` before trusting this list.
## Open threads
- Integrator: merge `session/deps-infra` → main; then existing worktrees need merge/rebase to pick up `bin/` + Brewfile + WARP.md.
- After live aider (old `.venv`) exits: `rm -rf /Users/linuslin/Desktop/ProjectOne/.venv`.
- T-002/T-003 and speech-track still open as before.
## Next actions
1. Integrator merges deps-infra branch.
2. Remove deprecated `.venv` when no process holds it.
3. Resume speech-track / profile / privacy when user is ready.
## Settled
- History/versioning via git, not append-only files (see WARP.md).
- Task intake default: single-agent triage; parallel worktrees are an escalation.
- System deps via Brewfile; Python CLIs via pipx; invoke through `bin/` wrappers (see WARP.md Dependency conventions).
