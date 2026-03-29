# Browser-First Platform Profile

This is the default platform profile for v1 of the harness.

## Intent

Optimize for the fastest closed loop you use today: local implementation, local browser execution, browser-based validation, and rapid iteration. This profile assumes many projects will be 2D, but it must not be treated as a universal truth.

## Runtime Defaults

| Topic | Default |
| --- | --- |
| Delivery target | A local build that runs in a browser |
| Gameplay bias | Often 2D, but optional |
| Input bias | Keyboard and mouse first unless the spec says otherwise |
| Validation surface | Browser automation, screenshots, manual playtesting, logic tests, integration tests, and performance checks |
| Portability stance | Browser first now, future platforms later through additional platform profiles |

## Required Delivery Expectations

- The build must be runnable locally with explicit commands.
- The game loop must be observable through the browser.
- Visual behavior must be reviewable with screenshots or equivalent browser evidence.
- Performance expectations must be stated in project-specific terms when they matter.
- Any deviation from keyboard/mouse-first assumptions must be called out in the spec.

## Non-Goals

- This profile does not choose a framework or engine.
- This profile does not force 2D mechanics on projects that need a different presentation.
- This profile does not set universal numeric performance budgets.

## Escalate When

- the design requires a non-browser primary runtime
- the project needs controller, touch, or multiplayer assumptions that materially change the default testing loop
- the game shape makes browser-first iteration a poor fit
