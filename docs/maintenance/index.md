# frequi: portable verification records

<!-- current-documentation-provenance -->
Documentation reviewed: 2026-10-13 / Git source base: `8e4b2a6f710e9eb6a58616729f491c50200fbf08` / [Current architecture and feature guide](../ayu-develop.md).
Historical execution commands/results below retain their original dates and scope; this metadata update is not a new application test run.
<!-- /current-documentation-provenance -->


Full raw logs are retained in the workspace maintenance evidence, not distributed here. Hashes identify those original logs. A successful build or selected test subset does not imply a full test-suite pass. Commands containing <workspace> describe the original execution environment.

[Machine-readable records](verification.json) · [Repository validation summary](../validation.md)

## Executed commands

| Check | Exit | Duration | Command | Outcomes |
| --- | ---: | ---: | --- | --- |
| browser-edge | 1 | 3.26s | `npx --yes pnpm@12.8.2 exec playwright test --project msedge --workers 2 --reporter line` | See exit status; no test-count assertion. |
| browser-edge-local | 1 | 25.0s | `npx --yes pnpm@12.8.2 exec playwright test --project=msedge` |   20 passed (23.0s) |
| browser-firefox-webkit | 1 | 93.22s | `npx --yes pnpm@12.8.2 exec playwright test --project firefox --project webkit --workers 2 --reporter line` |   39 passed (1.5m) |
| browser-firefox-webkit-baselines | 1 | 53.26s | `npx --yes pnpm@12.8.2 exec playwright test --project firefox --project webkit --workers 2 --reporter line` |   41 passed (51.6s) |
| browser-four-platforms | 0 | 107.79s | `npx --yes pnpm@12.8.2 exec playwright test --workers 2 --reporter line` |   84 passed (1.8m) |
| browser-three-platforms | 0 | 63.33s | `npx --yes pnpm@12.8.2 exec playwright test --project chromium --project firefox --project webkit --workers 2 --reporter line` |   63 passed (1.0m) |
| e2e-chromium | 1 | 54.29s | `npx --yes pnpm@12.8.2 exec playwright test --project chromium --workers 2 --reporter line` |   20 passed (49.2s) |
| e2e-chromium-baselines | 0 | 41.34s | `npx --yes pnpm@12.8.2 exec playwright test --project chromium --workers 2 --reporter line` |   21 passed (36.5s) |
| final-production-build | 0 | 5.22s | `npx --yes pnpm@12.8.2 run build` | See exit status; no test-count assertion. |
| final-unit-tests | 0 | 3.39s | `npx --yes pnpm@12.8.2 run test:unit --run` |  Test Files  12 passed (12)<br>      Tests  56 passed (56) |
| firefox-analysis-diagnosis | 1 | 16.69s | `npx --yes pnpm@12.8.2 exec playwright test e2e/analysis.spec.ts --project firefox --grep Lookahead analysis test --workers 1 --reporter line` | See exit status; no test-count assertion. |
| lint-final | 0 | 12.24s | `npx --yes pnpm@12.8.2 run lint-ci` | See exit status; no test-count assertion. |
| playwright-edge-install | 1 | 1.66s | `npx --yes pnpm@12.8.2 exec playwright install msedge` | See exit status; no test-count assertion. |
| playwright-extra-browsers | 0 | 25.91s | `npx --yes pnpm@12.8.2 exec playwright install firefox webkit` | See exit status; no test-count assertion. |
| typecheck | 0 | 18.35s | `npx --yes pnpm@12.8.2 typecheck` | See exit status; no test-count assertion. |
