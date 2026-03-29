# Tasks

## Checklist

- [x] Scaffold root navigation and source-of-truth docs
- [x] Author workflow, platform profile, role contracts, templates, and example run
- [x] Add Codex adapter skills and `agents/openai.yaml` files
- [x] Verify structure and content consistency

## Review

- Date: `2026-03-29`
- Outcome: harness scaffold implemented from an empty repo
- Verified:
  - all six role contracts contain the required standardized sections
  - all six Codex skills include source-contract links
  - all six `agents/openai.yaml` files reference the correct `$skill-name`
  - shared verdict states match between `docs/index.md` and `docs/templates/review-verdict.md`
  - browser-evidence guidance exists in the Game Developer, Play Tester, and Visual/Interaction Designer skills
  - the example artifact chain exists end-to-end under `docs/examples/comet-scrapyard-run/`
- Not run:
  - code tests or build checks, because this repo currently contains docs and adapter metadata only
