# Lessons

## 2026-03-29

### Do not document fallback flow as the primary operating model

- If the intended model is closed-loop orchestration, the README and prompts must say `invoke Producer once`.
- Manual specialist prompts belong in fallback or debug guidance only.

### Conservative approval beats optimistic approval for game one-shots

- Artifact completeness, screenshot presence, and passing unit tests are not enough.
- Approval must be blocked on obvious UI bugs, broken transitions, stacked screens, or clearly broken feel.
- If playability evidence is shallow or mixed, default to `changes_required`.

### First-session playability is a required gate

- Play Tester must explicitly assess the first few minutes for control responsiveness, survivability, pacing, and balance sanity.
- Mock Player must explicitly assess whether the game feels fair, fun, and worth continuing.
- Producer must not approve without both signals on playable builds.

### Do not assume the harness is only for greenfield work

- Existing projects need an intake phase before normal delegation.
- Brownfield mode should inspect current docs/code, classify artifacts, and run a targeted loop by default.
- Existing repo docs remain source material; the harness overlay under `./docs/project/` becomes the canonical working layer for the current loop.
