# Security Policy

## Scope

This repository contains **only** metadata: JSON manifests, JSON Schemas,
and Markdown documentation. There is no executable code, no build step,
and no runtime here. The security-relevant surface is limited to:

- The accuracy and integrity of `catalog/models.json` (does it point to
  the correct, legitimate repository for each model?).
- The correctness of the JSON Schemas, since MAGENAIS and other consumers
  validate model manifests against them before registering a model.

## What this catalog does NOT do

- It does not download, execute, `eval()`, or otherwise run any code from
  any listed repository. Discovery and installation are always explicit,
  user-initiated actions in the consuming application (e.g. MAGENAIS's
  Model Hub), never automatic.
- It does not host binaries, model weights, or executable artifacts.

## Trust levels

Every catalog entry declares a `trust` field:

| Level | Meaning |
|---|---|
| `magenais-verified` | Passed MAGENAIS's manifest, security, and reproducibility verification. |
| `community-verified` | Reviewed and vouched for by the community, not by MAGENAIS directly. |
| `experimental` | Functional and tested by its own author; not yet independently verified. |
| `unverified` | Listed for discovery only — use at your own risk. |

Consumers should treat `experimental` and `unverified` entries with the
same caution as any third-party code: read the source, run the tests
yourself, and do not grant elevated permissions or credentials to a model
you have not reviewed.

## Reporting a problem with a listing

If you find:
- a catalog entry pointing to a repository other than the one it claims,
- a manifest that doesn't match the JSON Schema,
- a listed license that doesn't match the actual repository's `LICENSE`
  file,
- or any other integrity issue with `catalog/models.json` or the schemas,

please open a private security advisory on this repository (GitHub →
Security → Report a vulnerability) rather than a public issue, so it can
be corrected before wider disclosure.

## Reporting a problem with a specific model's code

Security issues in an individual model's implementation (e.g.
`MAGENAIS-MODEL-DECISION-SCORE`) should be reported to that model's own
repository, using its own `SECURITY.md`.
