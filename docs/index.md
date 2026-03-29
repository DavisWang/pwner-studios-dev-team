# Pwner Studios Agent Harness

This repository packages a reusable agent operating system for indie game development.

## Defaults

| Topic | Default |
| --- | --- |
| Platform | Browser first |
| Genre bias | Usually 2D, but not required |
| Interaction bias | Keyboard and mouse first unless the spec says otherwise |
| Autonomy model | Supervised autonomy |
| Source of truth | `docs/` |
| Runtime-specific layer | `adapters/codex/skills/` |
| Entry modes | New project and existing project |

## Repository Map

| Path | Purpose |
| --- | --- |
| `docs/workflows/game-lifecycle.md` | Canonical project flow from brief to release/backlog |
| `docs/workflows/consistency-checklist.md` | Lightweight maintenance checks for keeping the harness aligned |
| `docs/contracts/platforms/browser-first.md` | Active default platform profile |
| `docs/contracts/roles/` | Vendor-neutral contracts for each role |
| `docs/templates/` | Canonical artifact templates |
| `docs/examples/comet-scrapyard-run/` | Minimal example artifact chain |
| `docs/examples/existing-project-run/` | Compact brownfield example with targeted artifact refresh |
| `adapters/codex/skills/` | Codex adapter layer derived from the contracts |

## Shared Verdict Vocabulary

| Status | Meaning |
| --- | --- |
| `draft` | Work exists but is not ready for review |
| `ready_for_review` | The owner believes the artifact is reviewable |
| `changes_required` | Reviewer found issues that must be addressed before proceeding |
| `approved` | Artifact is accepted for the next phase |
| `escalate_to_user` | Progress is blocked on a user decision |
| `deferred` | Work is intentionally parked for later follow-up |

## Usage Rules

- Treat `docs/` as the canonical source of truth.
- Treat the active platform profile as an input to every role contract.
- Use templates when creating new artifacts so handoffs stay legible to fresh agents.
- Use `00-existing-project-intake.md` before delegation when the repo already contains code and docs.
- Update the Codex adapter layer only after the source contract is correct.
