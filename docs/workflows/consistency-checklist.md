# Consistency Checklist

Use this checklist whenever the harness changes.

## Contract Alignment

- The six role names are identical in `docs/contracts/roles/` and `adapters/codex/skills/`.
- Every role contract includes the same section headers:
  `Mission`, `Active Platform Profile`, `Owned Artifacts`, `Required Inputs`, `Required Outputs`, `Non-Goals`, `Escalation Triggers`, `Handoff Targets`, `Acceptance Checks`.
- Every role contract references a platform profile instead of hardcoding runtime assumptions.
- Brownfield-capable contracts mention existing docs/code intake and targeted refresh behavior where relevant.

## Verdict Alignment

- The shared verdict states in `docs/index.md` match the template in `docs/templates/review-verdict.md`.
- Codex skills use the same verdict vocabulary and do not invent alternate status names.

## Escalation Alignment

- Producer escalation rules match the lifecycle doc.
- Specialist skills do not silently override the user-escalation boundaries defined in the contracts.
- Producer approval rules mention conservative signoff, not artifact-completion signoff.

## Adapter Alignment

- Each Codex skill links back to its source contract.
- Each `agents/openai.yaml` file names the correct `$skill-name` in `default_prompt`.
- Browser automation and screenshot guidance appears in the skills that review or validate browser behavior.
- Play Tester and Producer skills both mention navigation, UI sanity, and first-session playability as explicit gates.
- Mock Player skill mentions first-session fairness and responsiveness, not just vague fun feedback.
- README guidance covers both greenfield and existing-project invocation paths.
- The existing-project intake template exists and uses the fixed artifact-status vocabulary.
- Visual, developer, and play-tester guidance all treat the visual brief as the source of truth for animation style.
