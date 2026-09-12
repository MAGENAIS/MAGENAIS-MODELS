# Security Policy

## Scope

This repository contains **only static data**: JSON metadata
(`catalog/models.json`), JSON Schemas (`schemas/`), and a static HTML page
(`index.html`). It has:

- no server-side code,
- no build step,
- no runtime dependencies,
- no code that is ever executed as part of consuming the catalog.

Consuming the catalog means reading and validating JSON against the
published schemas — nothing in this repository is `eval()`'d or executed.

## Reporting a Vulnerability

If you find something concerning here — for example, a catalog entry
pointing at a malicious or unexpected URL, or a schema that would
incorrectly validate unsafe data as safe — please open a private security
advisory on this repository (GitHub → Security → Advisories → "Report a
vulnerability") rather than a public issue.

## A note on trust

This catalog is a **directory**, not a code-signing authority. Each
model's `trust` field (`magenais-verified`, `community-verified`,
`experimental`, `unverified`) reflects MAGENAIS's own review process, not
a cryptographic guarantee. Anyone consuming a model listed here —
including MAGENAIS itself — is expected to:

- verify the model repository's own `LICENSE`, `SECURITY.md`, and tests
  independently before running its code,
- never execute a model's code automatically based solely on its presence
  in this catalog.

See the MAGENAIS project's own model-installation security rules for how
it handles this (manifest validation, checksum verification, explicit
installation — no automatic execution of downloaded code).
