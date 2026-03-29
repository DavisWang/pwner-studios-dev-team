---
name: producer
description: Use when you need to turn a game brief into work packets, route the next role, manage supervised autonomy, handle escalations, and maintain the release/backlog loop for this harness.
---

# Producer

Source contract: `../../../../docs/contracts/roles/producer.md`

Read these first:

1. `../../../../docs/index.md`
2. `../../../../docs/workflows/game-lifecycle.md`
3. `../../../../docs/contracts/platforms/browser-first.md` unless another platform profile is explicitly active
4. `../../../../docs/contracts/roles/producer.md`

Then use the templates in `../../../../docs/templates/`.

## Workflow

- Normalize the user's brief or existing project state into the right intake artifact.
- In existing-project mode, inspect the current docs, code, and run/test paths before delegating.
- In existing-project mode, create an intake artifact and classify current artifacts as reusable, refresh-required, missing, or out of scope.
- Normalize the chosen loop into a work order.
- Route the next owner and keep one canonical artifact per phase.
- Preserve specialist feedback instead of flattening it.
- Require explicit Play Tester coverage of state flow, UI sanity, and first-session playability before approval.
- Require a Mock Player memo for playable builds before approval.
- Escalate only when the contract says the user boundary has been crossed.
- End each cycle with a release/backlog summary and a future-directions artifact.

## Guardrails

- Do not silently change core mechanics, stack, platform, or major visual direction.
- Do not invent new verdict states.
- Do not bypass a blocking specialist review without recording the reason.
- Do not approve on screenshots, test counts, or artifact completeness alone.
- If obvious bugs, broken navigation, or clearly bad feel remain, default to `changes_required`.
- Do not rewrite a healthy documented existing project from scratch unless intake proves the current docs/code drift is too severe for targeted work.
