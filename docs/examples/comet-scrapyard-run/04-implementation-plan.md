# Implementation Plan

## Build Shape

- top-down single-scene gameplay loop
- entity buckets for player, scrap, hazards, and pickup events
- one state layer for run flow and one for shop state

## Delivery Order

1. movement and collision loop
2. magnet beam and scrap attraction
3. cash-in flow and scoring
4. hazard escalation
5. shop upgrades
6. HUD and polish hooks

## Required Evidence

- local run command
- browser-playable build
- short implementation note for testers

## Known Risks

- magnet feel may need rapid iteration
- hazard readability may need visual feedback support

## Next Owner

- `Game Developer`
