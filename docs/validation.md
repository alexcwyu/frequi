# frequi: validation results

<!-- current-documentation-provenance -->
Documentation reviewed: 2026-10-13 / Git source base: `8e4b2a6f710e9eb6a58616729f491c50200fbf08` / [Current architecture and feature guide](ayu-develop.md).
Historical execution commands/results below retain their original dates and scope; this metadata update is not a new application test run.
<!-- /current-documentation-provenance -->


Build, typecheck, lint and complete existing unit/browser suites passed.

## Verified scope

56 Vitest tests and 84 Playwright cases across Chrome, Edge, Firefox and WebKit passed. Missing Darwin chart baselines for existing cases were visually inspected; no new cases were added.

Deliberate mocked login failures and browser/server teardown produce console warnings; a passing browser suite does not imply warning-free development-server output.

## Environment

Node with pnpm12.8.2

## Executed checks

Exploratory failures remain visible. Use later successful runs only for the scope they actually exercised; builds, syntax checks and benchmark smoke runs are distinct from complete test suites.

| Check | Exit | Duration | Command |
| --- | ---: | ---: | --- |
| browser-edge | 1 | 3.26s | `npx --yes pnpm@12.8.2 exec playwright test --project msedge --workers 2 --reporter line` |
| browser-edge-local | 1 | 25.0s | `npx --yes pnpm@12.8.2 exec playwright test --project=msedge` |
| browser-firefox-webkit | 1 | 93.22s | `npx --yes pnpm@12.8.2 exec playwright test --project firefox --project webkit --workers 2 --reporter line` |
| browser-firefox-webkit-baselines | 1 | 53.26s | `npx --yes pnpm@12.8.2 exec playwright test --project firefox --project webkit --workers 2 --reporter line` |
| browser-four-platforms | 0 | 107.79s | `npx --yes pnpm@12.8.2 exec playwright test --workers 2 --reporter line` |
| browser-three-platforms | 0 | 63.33s | `npx --yes pnpm@12.8.2 exec playwright test --project chromium --project firefox --project webkit --workers 2 --reporter line` |
| e2e-chromium | 1 | 54.29s | `npx --yes pnpm@12.8.2 exec playwright test --project chromium --workers 2 --reporter line` |
| e2e-chromium-baselines | 0 | 41.34s | `npx --yes pnpm@12.8.2 exec playwright test --project chromium --workers 2 --reporter line` |
| final-production-build | 0 | 5.22s | `npx --yes pnpm@12.8.2 run build` |
| final-unit-tests | 0 | 3.39s | `npx --yes pnpm@12.8.2 run test:unit --run` |
| firefox-analysis-diagnosis | 1 | 16.69s | `npx --yes pnpm@12.8.2 exec playwright test e2e/analysis.spec.ts --project firefox --grep Lookahead analysis test --workers 1 --reporter line` |
| lint-final | 0 | 12.24s | `npx --yes pnpm@12.8.2 run lint-ci` |
| playwright-edge-install | 1 | 1.66s | `npx --yes pnpm@12.8.2 exec playwright install msedge` |
| playwright-extra-browsers | 0 | 25.91s | `npx --yes pnpm@12.8.2 exec playwright install firefox webkit` |
| typecheck | 0 | 18.35s | `npx --yes pnpm@12.8.2 typecheck` |

## Portable evidence

[Executed command records](maintenance/index.html) · [Machine-readable verification](maintenance/verification.json) · [Engineering guide](ayu-develop.md) · [Development workflow](development.md)

Full original logs are retained in the workspace maintenance evidence; portable records contain their hashes, exact execution metadata and available outcome lines.
