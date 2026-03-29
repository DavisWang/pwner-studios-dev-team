# Pwner Studios Agent Harness

This repo is the central source of truth for the Pwner Studios game-agent harness.

Use it to:

- define and improve the team workflow
- define the role contracts
- define the artifact templates
- reference the harness from new and existing game repos

Do not use this repo as the place where game-specific artifacts live. Each game repo should keep its own brief, outputs, and code.

## The Operating Model

| Layer | Lives Here | What Belongs There |
| --- | --- | --- |
| Harness | This repo | workflow, contracts, templates, Codex adapter docs |
| Game repo | The target game workspace | brief or current docs, generated artifacts, implementation, tests, assets |

The main rule:

- Invoke the `Producer` once.
- The `Producer` owns delegation to the specialist agents.
- Do not manually invoke `Game Designer`, `Game Developer`, `Play Tester`, `Visual/Interaction Designer`, or `Mock Player` in the normal workflow.

## What You Need In A New Empty Game Repo First

You only need two files before the first invocation.

| File | Required | Purpose |
| --- | --- | --- |
| `AGENTS.md` | Yes | Local instructions for the specific game repo and a pointer back to this harness |
| `docs/project-brief.md` | Yes | The raw game brief: vision, constraints, references, and any must-have requirements |

Recommended starting shape:

```text
my-new-game/
├── AGENTS.md
└── docs/
    └── project-brief.md
```

After the first Producer run, the game repo should grow into this:

```text
my-new-game/
├── AGENTS.md
├── docs/
│   ├── project-brief.md
│   └── project/
│       ├── 01-work-order.md
│       ├── 02-game-spec.md
│       ├── 03-visual-direction.md
│       ├── 04-implementation-plan.md
│       ├── 05-build-note.md
│       ├── 06-test-verdict.md
│       ├── 07-mock-player-memo.md
│       ├── 08-release-backlog.md
│       └── 09-future-directions.md
```

## Minimal `AGENTS.md` For A New Game Repo

Use this in the new game repo.

```md
# Project Instructions

This repo uses the central Pwner Studios harness at:

`/Users/davis.wang/Documents/pwner-studios-dev-team`

Read these first:

1. `./docs/project-brief.md`
2. `/Users/davis.wang/Documents/pwner-studios-dev-team/docs/index.md`
3. `/Users/davis.wang/Documents/pwner-studios-dev-team/docs/workflows/game-lifecycle.md`
4. `/Users/davis.wang/Documents/pwner-studios-dev-team/docs/contracts/platforms/browser-first.md`

Defaults:

- Browser first unless the brief overrides it.
- Likely 2D, but not by force.
- Supervised autonomy.
- Store all project-specific outputs in `./docs/project/`.
- Start with the Producer.
```

## What To Put In `docs/project-brief.md`

Minimum useful contents:

- game idea in 3-8 bullets
- target player
- platform expectations
- hard constraints
- references or inspiration
- explicit must-have mechanics
- explicit out-of-scope items, if you already know them

If the brief is weak, the Producer and Game Designer can still work, but the first loop will be slower and more escalation-heavy.

## What You Need In An Existing Project Repo First

For existing projects, `docs/project-brief.md` becomes optional. The Producer should derive the current state from the repo and your request.

| File / state | Required | Purpose |
| --- | --- | --- |
| `AGENTS.md` | Yes | Local repo instructions plus a pointer back to this harness |
| Existing docs / README / run notes | Yes | Brownfield source material for current behavior and intent |
| Existing runnable codebase | Yes | The actual system the harness should inspect and improve |
| Inline user request | Yes | The requested feature, bug fix, or quality pass can live in the prompt |

Recommended starting shape:

```text
my-existing-game/
├── AGENTS.md
├── README.md
├── docs/ ...
└── src/ ...
```

After the Producer intake, the harness overlay should begin like this:

```text
my-existing-game/
├── AGENTS.md
├── README.md
├── docs/
│   ├── existing project docs...
│   └── project/
│       ├── 00-existing-project-intake.md
│       ├── 01-work-order.md
│       ├── 04-implementation-plan.md
│       ├── 06-test-verdict.md
│       ├── 07-mock-player-memo.md
│       ├── 08-release-backlog.md
│       └── 09-future-directions.md
```

Notes:

- Existing-project mode is targeted by default, so some numbered artifacts may remain absent if they were correctly marked `reusable`.
- Existing repo docs and code remain source material; `./docs/project/` is the canonical overlay for the current harness loop.

## The Right Way To Invoke The Harness

Open Codex in the new game repo, not in this harness repo.

Then paste this prompt:

```text
Use the central Pwner Studios harness at /Users/davis.wang/Documents/pwner-studios-dev-team.

Read:
- ./AGENTS.md
- ./docs/project-brief.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/index.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/workflows/game-lifecycle.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/contracts/platforms/browser-first.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/contracts/roles/producer.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/templates/work-order.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/templates/future-directions.md

Act as the Producer and own the full closed-loop workflow.

Create:
- ./docs/project/01-work-order.md

Rules:
- Assume browser-first unless the brief overrides it.
- Invoke specialist agents yourself as needed.
- Keep project-specific artifacts in ./docs/project/.
- Do not return control to me until the task is complete or a contract-defined escalation is required.
- Whenever you return control to me, include a bullet-point changelog.
- Whenever a runnable local preview exists, include a clickable local server URL so I can test immediately.
- Use conservative approval: basic bugs, broken navigation, obvious UI defects, or obviously bad feel must block approval even for v1.
- Normalize the brief into a work order.
- Produce or coordinate the remaining artifacts needed by the lifecycle.
- If something important is ambiguous, record the assumption or escalate only if it materially changes the game.
```

## The Right Way To Invoke The Harness For An Existing Project

Open Codex in the existing project repo, not in this harness repo.

Then paste this prompt:

```text
Use the central Pwner Studios harness at /Users/davis.wang/Documents/pwner-studios-dev-team.

This is an existing project, not a greenfield repo.

Read:
- ./AGENTS.md
- the current README and existing docs in this repo
- the current codebase and run/test paths
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/index.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/workflows/game-lifecycle.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/contracts/platforms/browser-first.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/contracts/roles/producer.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/templates/existing-project-intake.md
- /Users/davis.wang/Documents/pwner-studios-dev-team/docs/templates/work-order.md

Requested change:
- <describe the bug fix, feature, or quality pass here>

Act as the Producer and own the full closed-loop workflow.

Create:
- ./docs/project/00-existing-project-intake.md
- ./docs/project/01-work-order.md

Rules:
- Inspect the current repo before delegating.
- Capture the current playable state, docs reviewed, code areas reviewed, and current run/test commands.
- Classify artifacts as `reusable`, `refresh_required`, `missing`, or `out_of_scope`.
- Run a targeted loop only on the stale or request-affected areas.
- Do not rewrite the full artifact chain unless intake shows severe drift between docs, code, and behavior.
- Preserve existing working behavior unless the request explicitly changes it.
- Do not return control to me until the task is complete or a contract-defined escalation is required.
```

## Brownfield Artifact Flow

In existing-project mode, the Producer should not regenerate every artifact by default.

| Step | Owner | Typical Result |
| --- | --- | --- |
| 0 | Producer | Creates `./docs/project/00-existing-project-intake.md` |
| 1 | Producer | Creates `./docs/project/01-work-order.md` |
| 2 | Needed specialist roles only | Refresh only the stale or request-affected artifacts |
| 3 | Producer | Creates `./docs/project/08-release-backlog.md` and `./docs/project/09-future-directions.md` |

Typical refreshed artifacts in brownfield mode:

- `./docs/project/04-implementation-plan.md`
- `./docs/project/06-test-verdict.md`
- `./docs/project/07-mock-player-memo.md`

If the intake marks `02-game-spec.md` or `03-visual-direction.md` as `reusable`, the Producer should not regenerate them just to satisfy a full-chain ritual.

## What The Producer Should Do After Invocation

After you invoke the harness, the `Producer` should drive the rest of the loop without handing control back to you.

| Step | Owner | Expected Result |
| --- | --- | --- |
| 1 | Producer | Creates `./docs/project/01-work-order.md` |
| 2 | Producer -> Game Designer | Creates `./docs/project/02-game-spec.md` |
| 3 | Producer -> Visual/Interaction Designer | Creates `./docs/project/03-visual-direction.md` |
| 4 | Producer -> Game Developer | Creates `./docs/project/04-implementation-plan.md` and then implements the game |
| 5 | Producer -> Game Developer | Creates `./docs/project/05-build-note.md` |
| 6 | Producer -> Play Tester | Creates `./docs/project/06-test-verdict.md` |
| 7 | Producer -> Mock Player | Creates `./docs/project/07-mock-player-memo.md` |
| 8 | Producer | Creates `./docs/project/08-release-backlog.md` and `./docs/project/09-future-directions.md` |

The normal control flow is:

- you invoke the `Producer`
- the `Producer` invokes the other roles
- the `Producer` returns control only when the task is done or a valid escalation is needed
- when the `Producer` returns control, it should include a bullet changelog and a clickable local test URL when one exists
- Producer approval is expected to be conservative, not optimistic
- in existing-project mode, the `Producer` should inspect first, classify artifacts, and refresh only the necessary ones

## Manual Specialist Invocation Is Fallback Only

Manual invocation of specialist roles is for debugging, recovery, or controlled experimentation. It is not the intended operating model.

Use manual role prompts only if:

- you are testing one role in isolation
- the Producer loop failed and you need to recover a specific artifact
- you are iterating on the harness itself

Fallback examples:

| Role | Fallback Prompt |
| --- | --- |
| Game Designer | `Read ./docs/project/01-work-order.md and the central Game Designer contract. Create ./docs/project/02-game-spec.md.` |
| Visual/Interaction Designer | `Read ./docs/project/02-game-spec.md and the central Visual/Interaction Designer contract. Create ./docs/project/03-visual-direction.md.` |
| Game Developer | `Read ./docs/project/02-game-spec.md, ./docs/project/03-visual-direction.md, and the central Game Developer contract. Create ./docs/project/04-implementation-plan.md, then implement the game.` |
| Play Tester | `Read the build note, game spec, and central Play Tester contract. Create ./docs/project/06-test-verdict.md.` |
| Mock Player | `Read the spec, build evidence, and test verdict. Create ./docs/project/07-mock-player-memo.md with first-session fairness, responsiveness, and fun feedback.` |

## The Central Files To Reference

These are the main files both new and existing game repos should point at:

| Purpose | File |
| --- | --- |
| Harness map | `docs/index.md` |
| Lifecycle | `docs/workflows/game-lifecycle.md` |
| Default platform profile | `docs/contracts/platforms/browser-first.md` |
| Role contracts | `docs/contracts/roles/` |
| Templates | `docs/templates/` |
| Example artifact chain | `docs/examples/comet-scrapyard-run/` |
| Existing-project example | `docs/examples/existing-project-run/` |

## Important Clarifications

### 1. This repo is not automatically a global skill pack

The files under `adapters/codex/skills/` are adapter docs and metadata. A different repo can reference them, but they do not automatically become globally invocable `$producer`, `$game-designer`, and so on unless you later install or symlink them into your Codex skills directory.

### 2. Keep project outputs local

The harness stays here.

The game artifacts stay in the game repo.

That split is what gives you both:

- one central place to improve the harness
- one clean project history per game

### 3. The first failure mode to avoid

Do not manually orchestrate the specialists yourself.

If you start invoking Game Designer, Game Developer, or Play Tester directly as the primary flow, you become the orchestrator and the closed loop breaks.

### 4. The second failure mode to avoid

Do not approve on structural evidence alone.

Even for v1, the harness should block approval if:

- buttons or navigation are broken
- screens overlap or stack incorrectly
- text clips or overflows obviously
- the first few minutes feel clearly unfair, dead, or unreasonable

### 5. Animation style follows the brief

If the visual brief implies a specific art style for animation, that style is the source of truth.

- Do not fall back to line art or placeholder animation just because the needed sprites do not exist yet.
- If the animation needs new sprites or frames to match the brief, generate them.
- Play Tester should block approval if shipped animation visibly contradicts the brief's art style.

## If You Want The Easiest Reuse Path Later

The next useful upgrade is:

1. add a bootstrap script that creates the local `AGENTS.md` and `docs/project-brief.md`
2. optionally install or symlink the Codex role adapters so `$producer`-style invocation works from any repo
