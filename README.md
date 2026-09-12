# MAGENAIS-MODELS

Official catalog and discovery index for **MAGENAIS Models** — a set of
independent, open-source, research-oriented models that can be used on
their own or discovered and run through the [MAGENAIS](https://github.com/MAGENAIS)
Models Zoo.

This repository contains **no model algorithm code**. It is a directory:
metadata, manifests, and schemas that describe where each model lives and
how to interpret its inputs/outputs.

```
MAGENAIS-MODELS               (you are here — catalog only)
  │
  ├── MAGENAIS-MODEL-DECISION-SCORE   (independent repo, own releases)
  ├── MAGENAIS-MODEL-PATTERN-SENSE    (independent repo, own releases)
  └── MAGENAIS-MODEL-ANOMALY-MIND     (independent repo, own releases)
```

Each model above is a fully independent, standalone open-source project.
You can clone, install, test, and run any of them **without installing
MAGENAIS**. MAGENAIS itself is one consumer of this catalog among
potentially many.

## Why a separate catalog repository?

- Each model has independent versioning, releases, contributors, and
  licensing.
- This repo stays lightweight: pure JSON + Markdown, no build step, no
  runtime dependencies.
- Anyone — MAGENAIS or a third-party tool — can read `catalog/models.json`
  to discover what models exist, without needing to know anything about
  MAGENAIS internals.

## Catalog

The machine-readable catalog is [`catalog/models.json`](./catalog/models.json).
**It is currently an empty array `[]`** — no model repository has been
published yet. An entry is added here only once its independent
repository actually exists on GitHub and has a tagged release (see
[`catalog/models.example.json`](./catalog/models.example.json) for the
exact shape an entry takes, and [CONTRIBUTING.md](./CONTRIBUTING.md) for
how entries get added).

Roadmap (not yet in `catalog/models.json`):

| Model | ID | Status |
|---|---|---|
| DecisionScore | `magenais.decision-score` | Implemented, not yet published (repository prepared, GitHub publish pending) |
| PatternSense | `magenais.pattern-sense` | Not yet implemented |
| AnomalyMind | `magenais.anomaly-mind` | Not yet implemented |

*"Trust: experimental" means the model has not yet completed MAGENAIS's
verification process — see [Trust Levels](#trust-levels) below. It does
not mean the model is untested; each model repository has its own test
suite (see its README).*

## Schemas

- [`schemas/model-manifest.schema.json`](./schemas/model-manifest.schema.json) —
  the shape every model's `model.json` manifest must satisfy.
- [`schemas/model-response.schema.json`](./schemas/model-response.schema.json) —
  the shape every model's runtime output is normalized to.

These mirror the `ModelManifest` and `ModelResponse` TypeScript contracts
used internally by MAGENAIS, published here so any independent consumer
(not just MAGENAIS) can validate against the same contract.

## Trust levels

```
magenais-verified     — passed MAGENAIS's manifest, security, and
                         reproducibility verification process
community-verified    — reviewed and vouched for by the community,
                         not by MAGENAIS directly
experimental          — functional, tested by its own author, not yet
                         independently verified
unverified            — listed for discovery only, use at your own risk
```

## Using a model without MAGENAIS

*(Example below shows the intended flow for DecisionScore once its
repository is published — see the roadmap table above for current
status.)*

Every entry in the catalog links to an independent repository with its
own README, tests, and examples. Clone it directly:

```bash
git clone https://github.com/MAGENAIS/MAGENAIS-MODEL-DECISION-SCORE.git
cd MAGENAIS-MODEL-DECISION-SCORE
npm test
node examples/basic-usage.mjs
```

No MAGENAIS installation, account, API key, or network access is required
for any model currently listed here.

## Using a model through MAGENAIS

Inside MAGENAIS, open the **Models Zoo** tab to search, filter, and run
any listed model. MAGENAIS's `ModelRegistry`/`ModelRouter` consume this
catalog's manifests to make discovery and execution uniform across
models, regardless of which model repository they came from.

## Contributing / proposing a new model

See [CONTRIBUTING.md](./CONTRIBUTING.md). New model listings go through a
manifest-validation and security review before being added to
`catalog/models.json` — see [SECURITY.md](./SECURITY.md).

## License

This catalog's own content (schemas, `models.json`, documentation) is
licensed under [Apache-2.0](./LICENSE). Each listed model has its own
license, shown in its `catalog/models.json` entry and its own repository
— check there before use.

## Relationship to MAGENAIS Core

MAGENAIS Core (the closed-source proprietary application) is **not** part
of this repository and is not published here or anywhere public. This
catalog, and every model repository it lists, is fully independent of
MAGENAIS Core's proprietary source. MAGENAIS Core is simply one of
potentially many consumers of the open models listed here.
