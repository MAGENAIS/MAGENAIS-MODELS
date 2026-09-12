# MAGENAIS-MODELS

Official catalog and discovery index for **MAGENAIS Models** — a set of
independent, open-source, research-oriented models that can be used on
their own or discovered and run through the [MAGENAIS](https://github.com/MAGENAIS)
Models Zoo.

This repository does not contain model source code. Each model is its own
independently versioned, independently usable repository:

| Model | Repository | Status |
|---|---|---|
| DecisionScore | [MAGENAIS-MODEL-DECISION-SCORE](https://github.com/MAGENAIS/MAGENAIS-MODEL-DECISION-SCORE) | In development — not yet published |
| PatternSense | MAGENAIS-MODEL-PATTERN-SENSE | Planned |
| AnomalyMind | MAGENAIS-MODEL-ANOMALY-MIND | Planned |

See [`index.html`](./index.html) (published via GitHub Pages) for a
browsable version of this table, or [`catalog/models.json`](./catalog/models.json)
for the machine-readable version consumed by MAGENAIS's Models Zoo.

## What's in this repository

```
catalog/
  models.json                 Machine-readable catalog. Empty until a model publishes a v1.0.0 release.
schemas/
  model-manifest.schema.json  JSON Schema for a model's metadata (id, capabilities, license, trust, ...)
  model-response.schema.json  JSON Schema for what a model returns when run
index.html                    GitHub Pages landing page for this catalog
```

## Why the catalog starts empty

A model is only added to `catalog/models.json` once its own repository has
a tagged, tested, documented `v1.0.0` release — not while it's still being
built. This keeps the catalog trustworthy: every entry in it is something
you can actually clone and run today. Track upcoming models in the table
above or on the [website](./index.html) instead.

## Trust levels

Entries in the catalog carry one of:

- `magenais-verified` — passed MAGENAIS's own verification process
- `community-verified` — verified by community review
- `experimental` — working, but not yet verified
- `unverified` — use at your own risk

## License

This repository (catalog metadata and schemas) is licensed under
Apache-2.0 — see `LICENSE`. Each model repository has its own license,
shown in its own manifest; MAGENAIS Core (the private platform that
consumes this catalog) has a separate, proprietary license and is not
part of this repository or this license.

## Contributing

See `CONTRIBUTING.md`.

## Security

See `SECURITY.md`.
