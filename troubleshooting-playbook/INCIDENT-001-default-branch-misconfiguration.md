# INCIDENT-001 — GitHub Default Branch Misconfiguration

**Date:** 2026-03-13
**Severity:** P3
**Duration:** ~15 minutes
**Status:** Resolved

## Impact
Unable to create a Pull Request from `feature/day-1-foundation` into `main`. GitHub had set `feature/day-1-foundation` as the default branch instead of `main`.

## Detection
`gh pr create` command failed with error:
`must be on a branch named differently than "feature/day-1-foundation"`

## Timeline
- First push went to `feature/day-1-foundation` with no prior commit on `main`
- GitHub automatically set `feature/day-1-foundation` as default branch
- `gh pr create` failed because source and target branch were the same
- Created `main` branch locally and pushed to GitHub
- Changed default branch to `main` via GitHub Settings → General → Default branch
- Merged `feature/day-1-foundation` into `main` directly

## Root Cause
Repo was created without an initial commit on `main`. First pushed branch became the default.

## Resolution
Created `main` branch locally, pushed to GitHub, updated default branch in GitHub Settings, merged directly.

## Prevention
Always initialise the repo with a commit on `main` before creating any feature branches. Use `gh repo create --clone` which creates the repo but then immediately make a commit on `main` before branching.
