<!-- markdownlint-disable -->

# Hardening Report: fabasoad--twilio-voice-call-action/v3.0.6

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **fabasoad--twilio-voice-call-action/v3.0.6** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

All workflow files reference external actions or reusable workflows using mutable tags or branch names instead of pinned 40-character commit SHA digests. This exposes the action to supply-chain attacks where a compromised upstream tag or branch could inject malicious code. Failing references:
- functional-tests.yml: `actions/checkout@v6` (tag)
- linting.yml: `fabasoad/reusable-workflows/.github/workflows/wf-js-lint.yml@main` (branch), `fabasoad/reusable-workflows/.github/workflows/wf-pre-commit.yml@main` (branch)
- release.yml: `fabasoad/reusable-workflows/.github/workflows/wf-github-release.yml@main` (branch)
- security.yml: `fabasoad/reusable-workflows/.github/workflows/wf-security-sast.yml@main` (branch)
- sync-labels.yml: `fabasoad/reusable-workflows/.github/workflows/wf-sync-labels.yml@main` (branch)
- unit-tests.yml: `fabasoad/reusable-workflows/.github/workflows/wf-js-unit-tests.yml@main` (branch)
- update-license.yml: `fabasoad/reusable-workflows/.github/workflows/wf-update-license.yml@main` (branch)
All should be pinned to full 40-character SHA digests.

Locations:

- `.github/workflows/functional-tests.yml:20`
- `.github/workflows/linting.yml:13`
- `.github/workflows/linting.yml:16`
- `.github/workflows/release.yml:12`
- `.github/workflows/security.yml:15`
- `.github/workflows/sync-labels.yml:12`
- `.github/workflows/unit-tests.yml:18`
- `.github/workflows/update-license.yml:12`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all unpinned action references to full 40-character commit SHAs:
- functional-tests.yml: actions/checkout@v6 → @d23441a48e516b6c34aea4fa41551a30e30af803 # v6
- linting.yml (2 refs): fabasoad/reusable-workflows wf-js-lint.yml@main and wf-pre-commit.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- release.yml: fabasoad/reusable-workflows wf-github-release.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- security.yml: fabasoad/reusable-workflows wf-security-sast.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- sync-labels.yml: fabasoad/reusable-workflows wf-sync-labels.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- unit-tests.yml: fabasoad/reusable-workflows wf-js-unit-tests.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- update-license.yml: fabasoad/reusable-workflows wf-update-license.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main

