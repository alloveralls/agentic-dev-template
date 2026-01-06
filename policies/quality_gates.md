# Quality Gates
- Purpose: define concrete commands that must pass before merge. Align these with package scripts and CI.

## Lint
- Command: <e.g., `pnpm lint` / `eslint .` / `ruff check .`>
- Notes: <scope, config path, ignores>

## Format
- Command: <e.g., `pnpm format` / `prettier -w .` / `ruff format .` / `gofmt -w ./...`>
- Notes: <check vs write mode expectations>

## Test
- Command: <e.g., `pnpm test` / `vitest` / `pytest` / `go test ./...`>
- Notes: <coverage thresholds, slow/integration suites>

## Failure handling
- Policy: <e.g., fix and rerun required; exceptions require human approval (name/role)>
- Reporting: <how to record results in PR template/CI logs>
