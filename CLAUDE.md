# CLAUDE.md

## Repository Purpose

GitHub Action that extracts and outputs workflow context information (branch names, SHAs) for use in subsequent workflow steps.

**Outputs:** `base-branch`, `base-sha`, `head-branch`, `head-sha`, `default-branch`

## Known Structure

- `experiments/` — contains the action definition (`action.yml`) in development; deliberate working area
  - `experiments/superpowers/` — brainstorming specs and implementation plans from Claude sessions (gitignored, local only); check here for prior design decisions before starting new work
- `node_modules/` — exists locally but is gitignored; not committed to the repo

## Tooling

- GitHub Actions SHAs are manually verified and pinned — do not flag pinned SHAs as outdated without checking first
- Renovate: `renovate.json` in `.github/` is the repository-specific Renovate entry point; the `schedule` override there is intentional
- pre-commit hook runs `lint-staged` (Prettier + cspell) on `*.json`, `*.md`, `*.yml`
