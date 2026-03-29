# Pwner Studios Agent Harness

## Purpose

This repository is a reusable harness for browser-first indie game development with agent teams.

- `docs/` is the system of record.
- `adapters/codex/skills/` is a thin Codex execution layer derived from `docs/`.
- Browser is the default first platform. Most projects will likely be 2D, but that is a default bias, not a hard rule.

## Start Here

Read these files in order:

1. `docs/index.md`
2. `docs/workflows/game-lifecycle.md`
3. `docs/contracts/platforms/browser-first.md`
4. The relevant role contract in `docs/contracts/roles/`

## Operating Defaults

- Use supervised autonomy.
- Escalate to the user on core mechanic changes, stack or platform changes, major visual-direction changes, or unresolved cross-role conflicts.
- Update `docs/` first when behavior changes. Update `adapters/codex/skills/` second.
- Keep role names, verdict states, escalation rules, and platform-profile references aligned.

## Key Paths

- `docs/workflows/`: lifecycle and maintenance process
- `docs/contracts/roles/`: vendor-neutral role contracts
- `docs/contracts/platforms/`: platform profiles
- `docs/templates/`: reusable artifact templates
- `docs/examples/`: example artifact chain
- `adapters/codex/skills/`: Codex-specific role adapters
- `tasks/todo.md`: implementation checklist and review notes

## Editing Rules

- Do not turn role contracts into personas without hard outputs and gates.
- Keep platform assumptions parameterized through platform profiles.
- Preserve the shared verdict vocabulary from `docs/index.md`.
- If a contract changes, update the corresponding Codex skill in the same change.
