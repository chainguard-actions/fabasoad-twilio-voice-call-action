<!-- markdownlint-disable -->

# Hardening Report: fabasoad--twilio-voice-call-action/v3.0.2

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **fabasoad--twilio-voice-call-action/v3.0.2** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Multiple workflow files reference actions/reusable workflows using mutable tags or branch names instead of pinned 40-character commit SHAs. This exposes the workflow to supply-chain attacks if the referenced tag or branch is updated with malicious code.

Failing references:
- functional-tests.yml: `actions/checkout@v6` (tag)
- linting.yml: `fabasoad/reusable-workflows/.github/workflows/wf-js-lint.yml@main` (branch), `fabasoad/reusable-workflows/.github/workflows/wf-pre-commit.yml@main` (branch)
- release.yml: `fabasoad/reusable-workflows/.github/workflows/wf-github-release.yml@main` (branch)
- security.yml: `fabasoad/reusable-workflows/.github/workflows/wf-security-sast.yml@main` (branch)
- sync-labels.yml: `fabasoad/reusable-workflows/.github/workflows/wf-sync-labels.yml@main` (branch)
- unit-tests.yml: `fabasoad/reusable-workflows/.github/workflows/wf-js-unit-tests.yml@main` (branch)
- update-license.yml: `fabasoad/reusable-workflows/.github/workflows/wf-update-license.yml@main` (branch)

All `uses:` references should be pinned to a full 40-character hex commit SHA (e.g. `actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v4`).

Locations:

- `.github/workflows/functional-tests.yml:21`
- `.github/workflows/linting.yml:13`
- `.github/workflows/linting.yml:16`
- `.github/workflows/release.yml:11`
- `.github/workflows/security.yml:18`
- `.github/workflows/sync-labels.yml:13`
- `.github/workflows/unit-tests.yml:19`
- `.github/workflows/update-license.yml:12`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all 8 unpinned `uses:` references across 7 workflow files:
- functional-tests.yml: actions/checkout@v6 → @df4cb1c069e1874edd31b4311f1884172cec0e10 # v6
- linting.yml (×2): fabasoad/reusable-workflows wf-js-lint.yml@main and wf-pre-commit.yml@main → @4e2279474e598bee3ae8ded28899a24bbc7bf971 # main
- release.yml: fabasoad/reusable-workflows wf-github-release.yml@main → @4e2279474e598bee3ae8ded28899a24bbc7bf971 # main
- security.yml: fabasoad/reusable-workflows wf-security-sast.yml@main → @4e2279474e598bee3ae8ded28899a24bbc7bf971 # main
- sync-labels.yml: fabasoad/reusable-workflows wf-sync-labels.yml@main → @4e2279474e598bee3ae8ded28899a24bbc7bf971 # main
- unit-tests.yml: fabasoad/reusable-workflows wf-js-unit-tests.yml@main → @4e2279474e598bee3ae8ded28899a24bbc7bf971 # main
- update-license.yml: fabasoad/reusable-workflows wf-update-license.yml@main → @4e2279474e598bee3ae8ded28899a24bbc7bf971 # main

All SHAs were resolved via lookup_action_sha. Original tag/branch names preserved as inline comments.

