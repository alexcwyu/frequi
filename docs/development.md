# frequi: development workflow and layout

<!-- current-documentation-provenance -->
Documentation reviewed: 2026-10-13 / Git source base: `8e4b2a6f710e9eb6a58616729f491c50200fbf08` / [Current architecture and feature guide](ayu-develop.md).
Historical execution commands/results below retain their original dates and scope; this metadata update is not a new application test run.
<!-- /current-documentation-provenance -->


Use branch `feature/ayu_develop`. The actual upstream default branch and all fetched branch/tag identities are recorded in the maintenance sync evidence. Merge existing work; do not reset divergent branches or replace conflicting tags.

## Source synchronization

```sh
git fetch origin
git fetch upstream
git switch feature/ayu_develop
git merge origin/feature/ayu_develop
# Merge the actual default branch documented in the sync result.
```

This maintenance used namespaced remote tags before comparing tag identities. Missing upstream tags/branches were pushed to the fork; divergent branches were merged when conflict-free, and conflicting identities were retained for explicit reconciliation. The feature branch contains the default branch plus the maintenance changes. Source snapshot and architecture are documented in [ayu-develop.md](ayu-develop.md).

## Repository layout

- `docs/ayu-develop.md` and `docs/ayu-develop.html`: engineering guide with architecture, workflow, class and sequence diagrams and implementation links.
- `docs/development.md`: toolchain, layout and contributor workflow.
- `docs/validation.md`: exact executed commands, outcomes and limitations.

## Frontend toolchain

Use Node and the `packageManager`-declared pnpm12.8.2. A frozen installation, Vite production build, TypeScript typecheck, Vitest tests and mocked Playwright browser journeys are separate checks. Platform-specific chart snapshots were inspected before acceptance. Browser baselines are images for existing cases; no new test cases were added.

## Verification and documentation

Use the commands and results in [validation.md](validation.md). Markdown is the editable source of the guide; HTML embeds rendered SVG diagrams for offline browsing. Keep actual source links valid after moving modules. Preserve existing cases/assertions while correcting incompatible APIs, genuine resource leaks or invalid fixtures. No additional test cases were requested or added.

## Full browser verification

All 84 existing Playwright cases passed across Chromium with the Chrome channel, Microsoft Edge, Firefox and WebKit. The two missing Darwin chart baselines for each browser were visually checked before reuse. Run `pnpm exec playwright test --workers 2` after installing the configured browser channels.

If the official Edge app is installed in a user directory, set `PLAYWRIGHT_EDGE_EXECUTABLE_PATH` to its executable before running tests; otherwise Playwright uses its standard `msedge` channel installation. This maintenance used Microsoft Edge 155.0.4283.45 from the official signed installer. Original 404/401 login responses are deliberate mocked error cases; development-server teardown also emits router import warnings despite the complete passing suite.
