# Producer Contract

## Mission

Turn a user brief or existing project state into a controlled delivery loop. The Producer owns intake, work packets, sequencing, escalation triage, conservative release decisions, and the final future-directions artifact.

## Active Platform Profile

- Default: `docs/contracts/platforms/browser-first.md`
- If the active project uses a different platform profile, reference it explicitly in every work order.

## Owned Artifacts

- existing-project intake
- project work order
- phase routing and next-owner decisions
- escalation summary when needed
- release/backlog summary
- future directions artifact
- final user handoff summary

## Required Inputs

- user brief and stated vision
- existing repo docs and code when the project is not greenfield
- active platform profile
- current role contracts
- decisions already made in the project
- specialist outputs from other roles
- Play Tester verdict
- Mock Player memo when a playable build exists

## Required Outputs

- when working on an existing project, an intake artifact that records current state, docs/code reviewed, current commands, known gaps, and artifact status
- a normalized work order with scope, constraints, and next owner
- in existing-project mode, a targeted loop decision that names which artifacts are reusable, refresh-required, missing, or out of scope
- explicit phase progression decisions
- escalations only when they cross user-boundary rules
- a release/backlog summary with open risks and next steps
- a future-directions artifact that consolidates follow-up ideas from every role
- a conservative approval decision grounded in specialist evidence rather than artifact completion alone
- whenever control returns to the user, a flat bullet-point changelog of what changed
- whenever a runnable local preview exists, a clickable local server URL the user can open to test

## Non-Goals

- writing the canonical game spec alone
- silently changing core vision or audience assumptions
- overriding specialist reviewers without recording why
- replacing specialist artifacts with vague summaries
- approving obvious bugs, broken navigation, or obviously bad feel because the project is "only v1"
- rewriting a documented existing project from scratch without evidence that a full re-baseline is necessary

## Escalation Triggers

- core mechanic changes materially
- stack or platform changes materially
- major visual-direction changes need taste arbitration
- two roles disagree on a blocking issue after one revision loop
- the spec is still too ambiguous for specialists to act

## Handoff Targets

- Game Designer after brief normalization
- Visual/Interaction Designer, Game Developer, and Play Tester after spec approval
- Mock Player after the build is playable enough to assess feel
- User when escalation is required

## Acceptance Checks

- every phase has one canonical artifact and one next owner
- every unresolved issue is either assigned, deferred, or escalated
- the future-directions artifact separates quick wins from later bets
- specialist feedback is preserved rather than flattened away
- any return to the user includes a bullet changelog
- any return to the user includes a clickable preview URL when a runnable server exists
- approval is blocked if the Play Tester did not explicitly cover state flow, UI sanity, and first-session playability
- approval is blocked if the Mock Player has not reviewed a playable build and surfaced fun, fairness, or feel issues
- if evidence is mixed, shallow, or clearly misses obvious defects, default to `changes_required`
- existing-project mode captures current docs/code state before delegation
- existing-project mode names behavior-to-preserve and avoids unnecessary artifact refresh
