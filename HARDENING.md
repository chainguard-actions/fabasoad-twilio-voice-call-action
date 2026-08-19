<!-- markdownlint-disable -->

# Hardening Report: fabasoad--twilio-voice-call-action/v3.0.5

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **fabasoad--twilio-voice-call-action/v3.0.5** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Multiple workflow files reference external actions and reusable workflows using mutable tags or branch names instead of immutable 40-character commit SHA hashes. This exposes the action to supply-chain attacks where a compromised upstream repository could inject malicious code. Unpinned references found:
- functional-tests.yml: `actions/checkout@v6` (mutable tag)
- linting.yml: `fabasoad/reusable-workflows/.github/workflows/wf-js-lint.yml@main` and `wf-pre-commit.yml@main` (mutable branch)
- release.yml: `fabasoad/reusable-workflows/.github/workflows/wf-github-release.yml@main` (mutable branch)
- security.yml: `fabasoad/reusable-workflows/.github/workflows/wf-security-sast.yml@main` (mutable branch)
- sync-labels.yml: `fabasoad/reusable-workflows/.github/workflows/wf-sync-labels.yml@main` (mutable branch)
- unit-tests.yml: `fabasoad/reusable-workflows/.github/workflows/wf-js-unit-tests.yml@main` (mutable branch)
- update-license.yml: `fabasoad/reusable-workflows/.github/workflows/wf-update-license.yml@main` (mutable branch)
All should be pinned to full 40-character commit SHAs.

Locations:

- `.github/workflows/functional-tests.yml:20`
- `.github/workflows/linting.yml:13`
- `.github/workflows/linting.yml:16`
- `.github/workflows/release.yml:10`
- `.github/workflows/security.yml:18`
- `.github/workflows/sync-labels.yml:11`
- `.github/workflows/unit-tests.yml:20`
- `.github/workflows/update-license.yml:11`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all 8 unpinned action/workflow references to full 40-character commit SHAs:
- actions/checkout@v6 → @df4cb1c069e1874edd31b4311f1884172cec0e10 # v6 (functional-tests.yml)
- All 7 fabasoad/reusable-workflows@main references → @5ebe0938b8d8ef97bbb051004c511ba78449a866 # main (linting.yml ×2, release.yml, security.yml, sync-labels.yml, unit-tests.yml, update-license.yml)
Original tags/branch names preserved as inline comments for readability.

