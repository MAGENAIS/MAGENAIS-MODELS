# Contributing to MAGENAIS-MODELS

This repository is a **catalog**, not a place for model source code.
There are two kinds of contributions here:

1. Improving the catalog infrastructure itself (schemas, docs, tooling).
2. Proposing a new model listing (which lives in its **own** repository —
   only its manifest entry is added here).

## Improving the catalog

```bash
git clone https://github.com/MAGENAIS/MAGENAIS-MODELS.git
cd MAGENAIS-MODELS
```

Edit `README.md`, `schemas/*.json`, or `SECURITY.md`/`CONTRIBUTING.md` as
needed and open a pull request. Since there is no build step, please
double-check any JSON you touch with a formatter/validator before
submitting (e.g. `python -m json.tool catalog/models.json`).

## Proposing a new model listing

1. Your model must live in its own independent, public, open-source
   repository, following the structure MAGENAIS models use:
   `README.md`, `LICENSE`, `SECURITY.md`, `CONTRIBUTING.md`,
   `CHANGELOG.md`, `model.json`, `src/`, `tests/`, `examples/`, `docs/`.
2. Your `model.json` must validate against
   [`schemas/model-manifest.schema.json`](./schemas/model-manifest.schema.json).
3. Your model's runtime output must validate against
   [`schemas/model-response.schema.json`](./schemas/model-response.schema.json).
4. Open a pull request here adding **one entry** to
   `catalog/models.json` pointing to your repository, with `trust` set
   to `"unverified"` (MAGENAIS maintainers will update this after
   review — you should not set `magenais-verified` or
   `community-verified` yourself).
5. A maintainer will validate the manifest, do a basic security review
   (no arbitrary code execution paths, no obfuscated code, license
   matches what's declared), and merge if everything checks out.

## What will NOT be accepted

- Listings for repositories that require a mandatory paid account, API
  key, or cloud service just to run their published examples, unless
  clearly and honestly marked with `"pricing": {"type": "paid"}` (or
  `"enterprise"`) in the manifest.
- Listings that ship obfuscated or minified-only source with no readable
  original.
- Duplicate listings for the same model under a different name.
