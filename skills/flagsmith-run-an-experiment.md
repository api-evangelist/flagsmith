---
name: flagsmith-run-an-experiment
description: Set up and read a multivariate experiment on a Flagsmith feature — metric, variants,
  experiment, then exposures and results.
api: Flagsmith Management API
base_url: https://api.flagsmith.com/api/v1
auth: 'Authorization: Api-Key <Master API Key>'
generated: '2026-09-17'
method: generated
source: openapi/_original/flagsmith-api-openapi.json; operationIds grepped from that contract.
  https://docs.flagsmith.com/advanced-use/ab-testing
status: beta
operations:
  - create_feature
  - create_feature_multivariate_option
  - list_feature_multivariate_options
  - create_metric
  - list_metrics
  - create_experiment
  - list_experiments
  - get_experiment
  - get_experiment_exposures
  - get_experiment_results
  - update_experiment
---

# Run an experiment

> The experiment and metric operations are labelled **(Beta)** by Flagsmith. Shapes may change.

## The shape

An experiment runs on a **multivariate feature** — one with weighted `MultivariateOption` variants.
Variant assignment is hashed on the identity, so a given identity stays on the same variant across
calls. Metrics are **environment-scoped**; experiments are environment-scoped too, and **only one
active experiment per feature is allowed**.

## Steps

1. **Have a multivariate feature.** `create_feature` (`POST
   /api/v1/projects/{project_pk}/features/`), then add variants with
   `create_feature_multivariate_option` (`POST
   /api/v1/projects/{project_pk}/features/{feature_pk}/mv-options/`), each with its weight. Confirm
   with `list_feature_multivariate_options`.

2. **Define the metric.** `create_metric` (`POST
   /api/v1/environments/{environment_api_key}/experiment-metrics/`) with `name`, `description`,
   `aggregation`, `direction` (the expected direction of a good result) and an event `definition`.
   Check `list_metrics` first — it supports search via `q`.

3. **Create the experiment.** `create_experiment` (`POST
   /api/v1/environments/{environment_api_key}/experiments/`) with `feature`, `name`, `hypothesis`,
   and metrics attached inline. Refuse to create a second one on a feature that already has an active
   experiment — check `list_experiments` first, filtered by status.

4. **Read it back.** `get_experiment` for configuration and rollout state;
   `get_experiment_exposures` for variant exposure counts; `get_experiment_results` for statistical
   results.

   **Both exposure and result calls return `null` until they have been computed.** A `null` is not an
   error and not a zero — it means "not yet". Poll; do not report "no effect".

5. **Amend.** `update_experiment` changes only the name or the hypothesis. It does not change
   variants, metrics or weights.

## Rules this API imposes on you

- **Beta surface.** Flagsmith marks these operations Beta; do not build anything unattended on them
  without saying so.
- **No idempotency.** `create_metric` and `create_experiment` are POSTs with no dedupe key. After a
  timeout, re-read with `list_metrics` / `list_experiments` before retrying, or you will create
  duplicates — and a duplicate experiment on the same feature will be rejected anyway.
- **500 requests/minute** on the Management API. Polling for results is exactly the pattern that hits
  this, and there are no rate-limit headers to warn you. Back off on your own schedule.
- Errors are `{"message": "..."}` with no code.
