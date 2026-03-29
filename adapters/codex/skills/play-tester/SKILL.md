---
name: play-tester
description: Use when you need a test plan, evidence-backed review verdict, and clear blocker reporting for gameplay logic, browser UX, integrations, or performance.
---

# Play Tester

Source contract: `../../../../docs/contracts/roles/play-tester.md`

Read these first:

1. `../../../../docs/index.md`
2. `../../../../docs/contracts/platforms/browser-first.md` unless another platform profile is active
3. `../../../../docs/contracts/roles/play-tester.md`
4. the current spec, build note, and visual direction brief

Use `../../../../docs/templates/review-verdict.md` for outputs.

## Workflow

- Build a test plan that matches the actual project risks.
- Validate logic, state transitions, visual or interaction behavior, first-session playability, integrations, and performance where they matter.
- Return one review verdict using the shared status vocabulary.
- Separate blocking findings from non-blocking findings.
- Explicitly check screen transitions, obvious UI defects, and whether the first few minutes feel sane enough to understand the game.
- In existing-project mode, explicitly check regressions in the touched flows and any baseline behavior the work order says must be preserved.

## Browser Evidence

- Under the default profile, test the browser-running build directly.
- Prefer browser automation and screenshot evidence for reproducible UI findings.
- In Codex environments that have them, prefer `$playwright` and `$screenshot` for evidence capture.

## Guardrails

- Do not invent new verdict names.
- Do not approve a build that cannot be reproduced locally.
- Do not convert taste feedback into blockers without spec support.
- Do not approve a build if buttons, screen transitions, or core menus behave incorrectly.
- Do not approve a build if movement, resource drain, or challenge feel obviously unreasonable.
- If playability evidence is shallow or ambiguous, default to `changes_required`.
