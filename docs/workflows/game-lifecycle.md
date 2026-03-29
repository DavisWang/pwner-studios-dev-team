# Game Lifecycle

This is the canonical browser-first project flow for the harness. It supports both new-project and existing-project entry paths.

## Lifecycle

| Phase | Primary Owner | Canonical Artifact | Entry Gate | Exit Gate | Next Owner |
| --- | --- | --- | --- | --- | --- |
| Greenfield brief intake | Producer | Project work order | User brief exists and the repo is effectively greenfield | Brief is normalized, scoped, and tied to an active platform profile | Game Designer |
| Existing-project intake | Producer | Existing-project intake | Existing repo, current docs/code, and a user request exist | Current state is normalized, artifact status is classified, and the targeted loop is chosen | Producer |
| Brownfield work order | Producer | Project work order | Existing-project intake exists | Requested work is scoped, behavior-to-preserve is named, and only stale/missing artifacts are selected for refresh | Game Designer or Game Developer |
| Spec design | Game Designer | Canonical game spec | Work order approved | Spec is testable, scoped, and ambiguity is either resolved or escalated | Visual/Interaction Designer + Play Tester + Game Developer |
| Visual direction | Visual/Interaction Designer | Visual direction brief | Canonical spec approved | Interaction, readability, and sensory direction are concrete enough to implement | Game Developer |
| Implementation planning | Game Developer | Implementation plan | Canonical spec approved | Build approach, architecture boundaries, and delivery sequence are concrete | Game Developer |
| Build | Game Developer | Runnable build + implementation notes | Implementation plan approved | Local browser target runs and the implementation is ready for testing | Play Tester |
| Test and review | Play Tester | Review verdict | Runnable build exists | Acceptance checks are approved or blockers are returned with evidence | Producer |
| Experience sanity | Mock Player | Mock player memo | Playable build exists | First-session fun, fairness, and control feel are assessed with concrete feedback | Producer |
| Polish | Visual/Interaction Designer + Game Developer | Polish review + fix notes | Core build is functionally complete | Major UX and readability issues are resolved or escalated | Producer |
| Release and backlog | Producer | Release/backlog summary + future directions | Testing, mock-player, and polish outputs exist | Release recommendation is clear and follow-up items are logged | User or next project cycle |

## Control Rules

- Only one canonical artifact should represent phase completion.
- Each artifact must name the next owner.
- If two roles disagree on a blocking issue and neither can resolve it from the spec, the Producer decides whether to escalate to the user.
- Mock Player feedback is advisory input to the Producer, not an automatic phase gate.
- The Producer must use conservative approval: if evidence is weak or obviously misses a basic bug, playability issue, or screen-flow issue, the default is `changes_required`.
- A v1 prototype is still expected to have working buttons, sane navigation, no obvious UI breakage, and a playable first-session loop.
- Existing-project mode defaults to targeted refresh, not full re-baselining.
- Existing docs and code are source material; the harness overlay under `./docs/project/` is the canonical working layer for the current loop.
- Existing working behavior should be preserved unless the request explicitly changes it.

## Escalation Rules

Escalate to the user when any of the following happens:

- the core mechanic changes materially
- the project needs a different stack or platform than the active profile assumed
- the visual direction materially changes the intended tone
- the scope tradeoff changes the intended audience or quality bar
- two roles have unresolved blocking feedback after one revision loop

## Output Discipline

- Keep artifacts short enough for fresh agents to parse quickly.
- Separate facts from assumptions.
- Put unresolved questions in a dedicated section instead of scattering them through the document.
- Whenever control returns to the user, include a bullet-point changelog.
- Whenever a runnable local preview exists, include a clickable server URL so the user can test immediately.
- Play Tester outputs must explicitly cover navigation or state transitions, default-viewport UI sanity, and first-session playability.
- Producer approval must cite both Play Tester and Mock Player evidence for playable builds.
- Existing-project intake must capture docs reviewed, code areas reviewed, current run/test commands, artifact status, and targeted loop scope before delegation starts.
