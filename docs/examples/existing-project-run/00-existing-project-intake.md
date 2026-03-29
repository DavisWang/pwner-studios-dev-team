# Existing Project Intake

## Header

- Project: `Signal Path`
- Owner: `Producer`
- Date: `2026-03-29`
- Requested outcome: fix the title-to-game transition so screens do not stack and preserve the current puzzle loop
- Active platform profile: `docs/contracts/platforms/browser-first.md`

## Current Playable State

The game is playable in the browser and the puzzle loop works, but the title and gameplay screens currently render together instead of transitioning cleanly.

## Docs Reviewed

- `README.md`
- `docs/gameplay.md`
- `docs/ui-flow.md`

## Code Areas Reviewed

- `src/app.js`
- `src/shell.js`
- `styles.css`

## Current Run And Test Commands

- run: `npm run dev`
- test: `npm test`

## Known Bugs And Quality Gaps

- title and gameplay states stack instead of transitioning cleanly
- one menu button is visually clipped at smaller laptop heights

## Artifact Status

| Artifact | Status | Notes |
| --- | --- | --- |
| canonical game spec | `reusable` | current gameplay docs match behavior well enough |
| visual direction | `reusable` | no major style change requested |
| implementation plan | `refresh_required` | touched shell/state logic needs a targeted plan |
| review verdict | `missing` | must be regenerated after the fix |
| mock player memo | `missing` | must confirm the change does not harm the loop |

## Recommended Loop Scope

- refresh the implementation plan for shell/state flow only
- validate transition correctness and preserve the existing gameplay loop
- do not rewrite healthy docs or untouched systems
