# Implementation Plan

## Touched Subsystems

- shell state management
- title/menu transition logic
- small responsive CSS cleanup for the clipped button

## Compatibility Assumptions

- puzzle rules remain unchanged
- existing level and save data remain unchanged

## Delivery Order

1. inspect current shell state ownership
2. fix exclusive state transitions
3. patch the clipped button layout
4. validate no regression in puzzle start, reset, and return flows

## Next Owner

- `Game Developer`
