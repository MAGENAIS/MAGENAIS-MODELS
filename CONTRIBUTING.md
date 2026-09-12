# Contributing to MAGENAIS-MODELS

This repository is the catalog and discovery index for MAGENAIS Models —
it does not contain model source code. If you want to contribute a model
implementation, contribute to that model's own repository instead (see the
table in `README.md`).

## What you can contribute here

- **Corrections to `catalog/models.json`** — e.g. a broken repository
  link, a stale version number, an incorrect license or trust level for an
  already-published model.
- **Schema improvements** — proposals to `schemas/model-manifest.schema.json`
  or `schemas/model-response.schema.json`, if a field is missing or
  ambiguous for real-world models.
- **`index.html` improvements** — the GitHub Pages landing page.

## Adding a new model to the catalog

A model is added to `catalog/models.json` only once, by whoever maintains
this repository, and only after:

1. The model has its own public repository with a tagged `v1.0.0` (or
   later) release.
2. It has passing tests, a `LICENSE`, a `SECURITY.md`, and documentation.
3. Its `model.json` manifest validates against
   `schemas/model-manifest.schema.json`.

If you've built a model you'd like listed, open an issue linking to your
repository and its release — don't open a PR editing `catalog/models.json`
directly, since listing requires review of the model repository itself
first.

## Schema changes

Because `schemas/model-manifest.schema.json` and
`schemas/model-response.schema.json` mirror MAGENAIS's own internal
TypeScript contract (`src/models/types/ModelManifest.ts` and
`ModelResponse.ts`), a schema change here should be proposed alongside (or
after discussion with) that project — the two are meant to never drift
out of sync.

## Pull requests

1. Fork and branch from `main`.
2. Validate any `catalog/models.json` change against its schema before
   opening a PR.
3. Describe the change and why it's needed.

## Code of Conduct

Be respectful and constructive.
