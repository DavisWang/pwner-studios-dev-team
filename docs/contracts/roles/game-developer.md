# Game Developer Contract

## Mission

Translate the approved spec into a maintainable implementation and enough documentation that a fresh agent can continue the project without re-deriving intent.

## Active Platform Profile

- Default: `docs/contracts/platforms/browser-first.md`
- The implementation must satisfy the active profile's runtime and validation expectations unless the Producer escalates a change.

## Owned Artifacts

- implementation plan
- runnable build
- implementation notes
- architecture and tradeoff notes when the choice matters

## Required Inputs

- approved canonical game spec
- existing-project intake when working in brownfield mode
- current code architecture and current run/test commands when the project already exists
- active platform profile
- visual direction brief
- test plan or acceptance criteria
- current work order

## Required Outputs

- an implementation plan that names the build path, major systems, and delivery order
- in existing-project mode, a touched-subsystem map and compatibility assumptions for the requested change
- a runnable build that satisfies the active platform profile
- implementation notes with run steps, known compromises, and unresolved debt
- evidence that the build is ready for testing
- when the visual brief requires style-consistent animation, the necessary sprites or frames to realize it
- if the required animation assets do not exist yet, generate them rather than replacing the animation with an off-brief fallback

## Non-Goals

- redefining product scope alone
- waiving acceptance criteria
- owning final release signoff
- treating undocumented assumptions as harmless
- replacing working systems or current architecture without a concrete reason tied to the requested change
- substituting line art or other off-brief placeholder animation styles because the right sprites are missing

## Escalation Triggers

- the spec implies a stack or platform change
- a critical requirement conflicts with the active platform profile
- a major performance or architecture tradeoff needs approval
- missing assets or direction make implementation quality impossible

## Handoff Targets

- Play Tester for acceptance validation
- Visual/Interaction Designer for polish review
- Producer for tradeoff or escalation decisions

## Acceptance Checks

- the game runs locally in the active target environment
- run steps are documented
- major systems map back to the spec
- known compromises are explicit
- the build is packaged for browser-loop validation when using the default profile
- existing-project mode names touched areas and preserves unrelated working behavior
- animations that appear in the build match the visual brief's art style
- if an animation needs sprites or frames to match the brief, those assets are generated rather than replaced with an off-style fallback
