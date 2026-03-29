# Review Verdict Template

## Header

- Reviewer:
- Artifact reviewed:
- Date:
- Verdict:

## Allowed Verdicts

| Verdict | Use When |
| --- | --- |
| `draft` | The artifact is still being prepared and review is premature |
| `ready_for_review` | The owner is requesting formal review |
| `changes_required` | One or more issues block approval |
| `approved` | The artifact can move forward |
| `escalate_to_user` | A user decision is required before progress can continue |
| `deferred` | The issue is intentionally postponed |

## Blocking Findings

- finding

## Non-Blocking Findings

- finding

## Session Coverage

- startup path covered:
- title, menu, and transition path covered:
- first-session gameplay minutes covered:
- retry, fail, or recovery path covered:

## Navigation And State Flow

- note whether screens, menus, and gameplay states transition correctly and exclusively

## UI And Visual Sanity

- note any clipping, overflow, blocked buttons, overlapping layers, unreadable text, or obvious layout defects

## Playability And Balance Sanity

- note whether the game feels controllable, survivable, readable, and reasonably paced in the first session
- if balance or feel is obviously broken, explain why that is blocking

## Baseline And Regression Check

- note what prior behavior was expected to stay working
- note any regressions introduced by the requested change

## Evidence

- artifact, screenshot, reproduction notes, or measurement

## Required Changes

- change

## Next Owner

- role
