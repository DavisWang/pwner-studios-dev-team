# Existing Project Example Run

This directory shows a compact brownfield loop.

## Scenario

An existing browser puzzle game already has code, a README, and gameplay docs. The request is to fix a broken screen transition, preserve the rest of the loop, and avoid rewriting healthy project docs.

## Artifact Strategy

This is targeted-update mode, not full re-baselining.

Artifacts omitted from this example were intentionally classified as `reusable`.

## Artifact Chain

| Order | Artifact | Primary Owner | Why It Exists |
| --- | --- | --- | --- |
| 00 | Existing-project intake | Producer | Normalize current state before delegation |
| 01 | Work order | Producer | Scope the requested fix and behavior to preserve |
| 04 | Implementation plan | Game Developer | Refresh only the touched implementation plan |
| 06 | Test verdict | Play Tester | Validate the fix and check regressions |
| 07 | Mock player memo | Mock Player | Judge whether the change helps or harms the current loop |
| 08 | Release/backlog summary | Producer | Close the targeted loop |
| 09 | Future directions | Producer | Capture the next small bets after the targeted fix |
