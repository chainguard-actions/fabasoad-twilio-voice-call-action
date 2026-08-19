<!-- markdownlint-disable -->

# Hardening Report: fabasoad--twilio-voice-call-action/v3.0.4

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **fabasoad--twilio-voice-call-action/v3.0.4** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Multiple workflow files reference actions/reusable workflows by mutable tag or branch name instead of a full 40-character commit SHA. This exposes the action to supply-chain attacks where a tag or branch can be silently updated to point to malicious code.

Failing references:
- .github/workflows/functional-tests.yml: `uses: actions/checkout@v6` (tag)
- .github/workflows/linting.yml: `uses: fabasoad/reusable-workflows/.github/workflows/wf-js-lint.yml@main` (branch)
- .github/workflows/linting.yml: `uses: fabasoad/reusable-workflows/.github/workflows/wf-pre-commit.yml@main` (branch)
- .github/workflows/release.yml: `uses: fabasoad/reusable-workflows/.github/workflows/wf-github-release.yml@main` (branch)
- .github/workflows/security.yml: `uses: fabasoad/reusable-workflows/.github/workflows/wf-security-sast.yml@main` (branch)
- .github/workflows/sync-labels.yml: `uses: fabasoad/reusable-workflows/.github/workflows/wf-sync-labels.yml@main` (branch)
- .github/workflows/unit-tests.yml: `uses: fabasoad/reusable-workflows/.github/workflows/wf-js-unit-tests.yml@main` (branch)
- .github/workflows/update-license.yml: `uses: fabasoad/reusable-workflows/.github/workflows/wf-update-license.yml@main` (branch)

All `uses:` references should be pinned to a full 40-character hex commit SHA (e.g. `actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v4`).

Locations:

- `.github/workflows/functional-tests.yml:21`
- `.github/workflows/linting.yml:14`
- `.github/workflows/linting.yml:17`
- `.github/workflows/release.yml:11`
- `.github/workflows/security.yml:17`
- `.github/workflows/sync-labels.yml:12`
- `.github/workflows/unit-tests.yml:19`
- `.github/workflows/update-license.yml:11`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all 8 unpinned action references to full commit SHAs:
- functional-tests.yml: actions/checkout@v6 → @d23441a48e516b6c34aea4fa41551a30e30af803 # v6
- linting.yml (2 refs): fabasoad/reusable-workflows@main → @10062f8186847226cb4865efbb8047795d372bae # main (wf-js-lint.yml and wf-pre-commit.yml)
- release.yml: fabasoad/reusable-workflows@main → @10062f8186847226cb4865efbb8047795d372bae # main (wf-github-release.yml)
- security.yml: fabasoad/reusable-workflows@main → @10062f8186847226cb4865efbb8047795d372bae # main (wf-security-sast.yml)
- sync-labels.yml: fabasoad/reusable-workflows@main → @10062f8186847226cb4865efbb8047795d372bae # main (wf-sync-labels.yml)
- unit-tests.yml: fabasoad/reusable-workflows@main → @10062f8186847226cb4865efbb8047795d372bae # main (wf-js-unit-tests.yml)
- update-license.yml: fabasoad/reusable-workflows@main → @10062f8186847226cb4865efbb8047795d372bae # main (wf-update-license.yml)

