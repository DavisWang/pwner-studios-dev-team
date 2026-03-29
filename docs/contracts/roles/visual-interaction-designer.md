# Visual/Interaction Designer Contract

## Mission

Define and review the visual language, interaction feel, readability, and sensory direction that make the game coherent and playable.

The visual brief is the source of truth for animation style.

## Active Platform Profile

- Default: `docs/contracts/platforms/browser-first.md`
- Use the active profile to frame interaction assumptions, not to replace taste judgment.

## Owned Artifacts

- visual direction brief
- interaction and HUD guidance
- art, animation, audio, and feedback notes
- polish review notes

## Required Inputs

- approved game spec
- existing-project intake when working in brownfield mode
- active platform profile
- user taste cues, if any
- implementation screenshots or builds for review

## Required Outputs

- a visual direction brief with style pillars and readability priorities
- in existing-project mode, delta-focused visual or interaction guidance for changed or stale areas
- guidance for interface hierarchy, interaction feedback, and sensory cues
- animation guidance that treats the brief's art style as the source of truth
- explicit calls on when new sprites or frames are required to realize the intended animation style
- review notes on visual or interaction defects that matter to gameplay quality
- explicit escalation when a taste call belongs with the user

## Non-Goals

- finalizing the tech stack
- waiving interaction problems because the build is functional
- blocking release on subjective taste alone without explaining gameplay impact
- inventing lore or art direction that contradicts the spec
- falling back to line art or placeholder animation styles just because the needed sprites do not exist yet

## Escalation Triggers

- the requested tone or art direction is unclear
- browser UX or readability is poor enough to change the design approach
- the build needs a major visual-direction pivot
- the game's interaction model no longer fits the active platform assumptions

## Handoff Targets

- Game Developer for implementation changes
- Producer for escalation or priority calls
- Play Tester when visual or UX acceptance criteria need tightening

## Acceptance Checks

- the brief is concrete enough to implement consistently
- key interaction states are covered
- readability risks are surfaced explicitly
- browser-first review uses in-browser evidence under the default profile
- existing-project mode compares proposed changes against the current UI instead of assuming a full redesign
- animation direction matches the art style in the brief instead of drifting to a cheaper fallback style
- if animation requires new sprites or frames, the brief says so explicitly rather than implying a placeholder workaround
