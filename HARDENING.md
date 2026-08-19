<!-- markdownlint-disable -->

# Hardening Report: fabasoad--twilio-voice-call-action/v3.0.3

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **fabasoad--twilio-voice-call-action/v3.0.3** was hardened automatically. 7 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

Workflow uses actions/checkout@v6 — a mutable version tag, not a pinned SHA. An attacker who compromises the upstream action could inject malicious code.

Locations:

- `.github/workflows/functional-tests.yml:21`

### unpinned-uses (severity: high)

Workflow uses fabasoad/reusable-workflows/.github/workflows/wf-js-lint.yml@main and fabasoad/reusable-workflows/.github/workflows/wf-pre-commit.yml@main — mutable branch refs, not pinned SHAs. Any push to the upstream `main` branch could silently change what code runs.

Locations:

- `.github/workflows/linting.yml:14`
- `.github/workflows/linting.yml:17`

### unpinned-uses (severity: high)

Workflow uses fabasoad/reusable-workflows/.github/workflows/wf-github-release.yml@main — a mutable branch ref, not a pinned SHA.

Locations:

- `.github/workflows/release.yml:11`

### unpinned-uses (severity: high)

Workflow uses fabasoad/reusable-workflows/.github/workflows/wf-security-sast.yml@main — a mutable branch ref, not a pinned SHA.

Locations:

- `.github/workflows/security.yml:19`

### unpinned-uses (severity: high)

Workflow uses fabasoad/reusable-workflows/.github/workflows/wf-sync-labels.yml@main — a mutable branch ref, not a pinned SHA.

Locations:

- `.github/workflows/sync-labels.yml:12`

### unpinned-uses (severity: high)

Workflow uses fabasoad/reusable-workflows/.github/workflows/wf-js-unit-tests.yml@main — a mutable branch ref, not a pinned SHA.

Locations:

- `.github/workflows/unit-tests.yml:19`

### unpinned-uses (severity: high)

Workflow uses fabasoad/reusable-workflows/.github/workflows/wf-update-license.yml@main — a mutable branch ref, not a pinned SHA.

Locations:

- `.github/workflows/update-license.yml:11`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned all mutable action references to full commit SHAs:
- functional-tests.yml: actions/checkout@v6 → @d23441a48e516b6c34aea4fa41551a30e30af803 # v6
- linting.yml: wf-js-lint.yml@main and wf-pre-commit.yml@main → @c5bd8945762dab6d2f5168b65f10355887ea40a3 # main
- release.yml: wf-github-release.yml@main → @c5bd8945762dab6d2f5168b65f10355887ea40a3 # main
- security.yml: wf-security-sast.yml@main → @c5bd8945762dab6d2f5168b65f10355887ea40a3 # main
- sync-labels.yml: wf-sync-labels.yml@main → @c5bd8945762dab6d2f5168b65f10355887ea40a3 # main
- unit-tests.yml: wf-js-unit-tests.yml@main → @c5bd8945762dab6d2f5168b65f10355887ea40a3 # main
- update-license.yml: wf-update-license.yml@main → @c5bd8945762dab6d2f5168b65f10355887ea40a3 # main

Original tags/branch names preserved as inline comments. linting.yml was rewritten after sequential edits caused file corruption.

