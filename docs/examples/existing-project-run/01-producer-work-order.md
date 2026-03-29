# Producer Work Order

- Project: `Signal Path`
- Work order ID: `SP-014`
- Requester: `User`
- Owner: `Game Developer`
- Project mode: `existing project`
- Phase: `targeted update`
- Active platform profile: `docs/contracts/platforms/browser-first.md`

## Objective

Fix the broken title-to-game transition without changing the core puzzle rules or the current art direction.

## Requested Change

Make title, menu, and gameplay states transition exclusively instead of stacking on the same page.

## Existing Behavior To Preserve

- the current puzzle loop
- current level data
- current visual language

## In Scope

- shell state and screen transition logic
- any small CSS or layout fixes needed to make the transition correct

## Out Of Scope

- rule changes
- new content
- visual redesign

## Inputs

- `00-existing-project-intake.md`
- current repo docs and shell implementation

## Artifact Status Inputs

| Artifact | Status | Notes |
| --- | --- | --- |
| implementation plan | `refresh_required` | shell/state logic changed |
| review verdict | `missing` | must be recreated |
| mock player memo | `missing` | must be recreated |

## Required Outputs

- refreshed implementation plan
- fixed transition behavior in code
- review verdict
- mock player memo

## Constraints

- preserve existing gameplay
- preserve current platform profile
- keep the loop targeted

## Escalation Boundary

Escalate only if the fix requires rewriting the shell architecture or materially changing the existing UI direction.

## Done When

- title/menu/gameplay states are exclusive
- no obvious regression exists in the core puzzle loop

## Next Owner

- `Game Developer`
