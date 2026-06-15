# Contributing to sciqnt

This is the **org-wide default** contribution guide (a repo with its own
`CONTRIBUTING.md` overrides it). sciqnt is a **component world**: each piece — the
contract, the libraries, the apps, and **every connector** — is its own repo, open
under this org, governed by one shared constitution.

## The constitution governs everything

How every repo is built and reviewed lives in **[`sq-constitution`](https://github.com/sciqnt/sq-constitution)**:
`PRINCIPLES.md` (the 18-principle constitution), `PRINCIPLE_REVIEW.md` (the review
rubric), and the **reusable CI/review/triage workflows** every repo inherits. Read it
once; it applies everywhere. Decisions go in the direction of the principles.

## How a PR works (the same in every repo)

1. **CI — the mechanical gate.** Tests + conformance run on every PR. Green is required.
2. **The principle-review agent — the judgment gate.** An agent reviews your diff
   against the constitution and posts an advisory review. A trusted-author, CI-green,
   `ALIGNED` PR can auto-merge; everything else waits for a human. Community PRs always
   get a human.
3. A maintainer can summon a fix by commenting **`@claude <instruction>`** on the PR.

## Ground rules

- **DCO, not CLA — permanently.** Sign off (`git commit -s`); you keep your copyright.
  sciqnt will never ask for a CLA. The code is **MIT and stays MIT**.
- **Conformance is the bar.** A unit "passes" only when it passes the conformance suite
  against its targeted contract version.
- **Money is `Decimal`, currency mandatory, bitemporal** — the deterministic core is held
  to a stricter bar.
- **Synthetic fixtures only** — never real account data or credentials.

## Contributing a connector (the most valuable contribution)

A connector maps one broker / exchange / data source into the canonical schema. Start
from **`sq-connector-template`** (or tell your coding agent "build a sciqnt connector
for &lt;broker&gt;"). A connector is **interoperability** — it reads the *user's own
account with their own credentials, locally*. Keep it on the right side of that:
**own-account only, never circumvent an access control**, nominative trademark use, and
ship an accurate `NOTICE.md` (not affiliated / not endorsed). See the connector
template + `sq-contract` for the contract + conformance harness.

## Everything else

Bugs and small fixes: open a PR with a test. Features: open an issue first — the
constitution governs (e.g. presentation never computes; every view ships a `--json`
data form; no credential custody, ever).
