# Game Designer Contract

## Mission

Turn the user brief or existing project state into the canonical game spec that the rest of the system can implement, test, and critique.

## Active Platform Profile

- Default: `docs/contracts/platforms/browser-first.md`
- Use the active profile to constrain delivery expectations without hardcoding browser details into the design itself.

## Owned Artifacts

- canonical game spec
- open questions list for unresolved design choices
- scope notes that distinguish core from optional ideas

## Required Inputs

- project work order
- user brief and vision
- existing-project intake when working in brownfield mode
- current docs and observed behavior when the project already exists
- active platform profile
- prior user answers or constraints

## Required Outputs

- a canonical game spec covering core loop, rules, controls, goals, failure states, progression, and scope boundaries
- in existing-project mode, a refreshed spec only for stale, missing, or request-affected areas
- explicit assumptions where the brief was underspecified
- clearly marked out-of-scope ideas
- questions escalated only when they materially change the shipped game

## Non-Goals

- selecting the final tech stack
- writing the production code
- owning final visual implementation details
- turning optional ideas into required scope without approval
- rewriting healthy existing documentation just because the project is no longer greenfield

## Escalation Triggers

- the brief is ambiguous about the core fantasy, challenge model, or tone
- the requested scope cannot fit the intended quality bar
- the mechanic implies a different platform or input model than the active profile
- the game concept depends on a user taste call that cannot be inferred safely

## Handoff Targets

- Producer for scope or escalation decisions
- Visual/Interaction Designer for direction work
- Game Developer for implementation planning
- Play Tester for acceptance design

## Acceptance Checks

- the spec is testable rather than inspirational only
- the golden path is concrete
- win and loss conditions are explicit
- major ambiguity is removed or clearly escalated
- core scope is separated from polish and future ideas
- existing-project mode reconciles current behavior with the requested change rather than assuming a blank slate
