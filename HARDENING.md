<!-- markdownlint-disable -->

# Hardening Report: fabasoad--twilio-voice-call-action/v3.0.7

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **fabasoad--twilio-voice-call-action/v3.0.7** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Multiple workflow files reference actions/reusable workflows using mutable tags or branch names instead of pinned 40-character commit SHAs, making them vulnerable to supply-chain attacks. Failing references: functional-tests.yml uses actions/checkout@v6 (tag); linting.yml uses fabasoad/reusable-workflows wf-js-lint.yml@main and wf-pre-commit.yml@main (branch); release.yml uses wf-github-release.yml@main (branch); security.yml uses wf-security-sast.yml@main (branch); sync-labels.yml uses wf-sync-labels.yml@main (branch); unit-tests.yml uses wf-js-unit-tests.yml@main (branch); update-license.yml uses wf-update-license.yml@main (branch). All references should be pinned to a full 40-character hex commit SHA.

Locations:

- `.github/workflows/functional-tests.yml:22`
- `.github/workflows/linting.yml:14`
- `.github/workflows/linting.yml:17`
- `.github/workflows/release.yml:11`
- `.github/workflows/security.yml:19`
- `.github/workflows/sync-labels.yml:11`
- `.github/workflows/unit-tests.yml:19`
- `.github/workflows/update-license.yml:11`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all unpinned action references to full 40-character commit SHAs:
- functional-tests.yml: actions/checkout@v6 → @d23441a48e516b6c34aea4fa41551a30e30af803 # v6
- linting.yml: fabasoad/reusable-workflows wf-js-lint.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- linting.yml: fabasoad/reusable-workflows wf-pre-commit.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- release.yml: fabasoad/reusable-workflows wf-github-release.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- security.yml: fabasoad/reusable-workflows wf-security-sast.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- sync-labels.yml: fabasoad/reusable-workflows wf-sync-labels.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- unit-tests.yml: fabasoad/reusable-workflows wf-js-unit-tests.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
- update-license.yml: fabasoad/reusable-workflows wf-update-license.yml@main → @10062f8186847226cb4865efbb8047795d372bae # main
All original tags/branches preserved as inline comments for readability.

