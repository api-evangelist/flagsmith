---
name: flagsmith-ship-a-flag
description: Create a feature flag in a Flagsmith project and turn it on in one environment, taking
  the correct path for that environment's feature-versioning mode.
api: Flagsmith Management API
base_url: https://api.flagsmith.com/api/v1
auth: 'Authorization: Api-Key <Master API Key>'
generated: '2026-09-17'
method: generated
source: openapi/_original/flagsmith-api-openapi.json; every operationId below was grepped from that
  contract. https://docs.flagsmith.com/managing-flags/feature-versioning
operations:
  - list_organizations
  - list_projects_in_organization
  - list_project_environments
  - create_feature
  - list_project_features
  - get_environment_feature_versions
  - create_environment_feature_version
  - create_environment_feature_version_state
  - publish_environment_feature_version
  - update_environment_feature_state
---

# Ship a flag

## Before you start

Flagsmith has two API surfaces and they take different keys. This skill uses the **Management API**
at `https://api.flagsmith.com/api/v1` with `Authorization: Api-Key <key>`. The `Api-Key ` prefix is
required — a bare key is rejected. Do not use the client-side `X-Environment-Key` here; that belongs
to the SDK/Flags API on `edge.api.flagsmith.com`.

## The fork you must resolve first

Every environment carries `use_v2_feature_versioning`. It decides which operations apply, and getting
it wrong is the most common failure on this API.

- **false (v1)** — feature state is edited in place.
- **true (v2)** — feature state is immutable inside a version; you create a version, set states on
  it, then publish it.

Read it from the environment before you write anything.

## Steps

1. **Find the project.** `list_organizations` → `list_projects_in_organization` (`GET
   /api/v1/organisations/{id}/projects/`). Keep the project's integer `id`.

2. **Find the environment.** `list_project_environments` (`GET /api/v1/projects/{id}/environments/`).
   Keep **both** identifiers — the integer `id` and the `api_key` string. Routes are inconsistent
   about which they take: `{environment_pk}` wants the integer, `{environment_api_key}` wants the
   string. Also read `use_v2_feature_versioning`.

3. **Create the feature.** `create_feature` (`POST /api/v1/projects/{project_pk}/features/`) with a
   `name`. The feature is a project-level definition — creating it does not turn anything on
   anywhere. Confirm with `list_project_features`.

4. **Turn it on.**

   *If `use_v2_feature_versioning` is false:*
   `update_environment_feature_state` (`PUT
   /api/v1/environments/{environment_api_key}/featurestates/{id}/`) with `enabled: true` and any
   `feature_state_value`. This write lands immediately and live.

   *If `use_v2_feature_versioning` is true:*
   - `create_environment_feature_version` (`POST
     /api/v1/environments/{environment_pk}/features/{feature_pk}/versions/`)
   - `create_environment_feature_version_state` on that version, with `enabled` and the value
   - `publish_environment_feature_version` (`POST .../versions/{id}/publish/`) — **nothing is live
     until this call**

5. **Verify.** `get_environment_feature_versions` and check `is_live` on the version you published,
   or re-read the feature state.

## Rules this API imposes on you

- **No idempotency.** There is no `Idempotency-Key` header anywhere on this API. `create_feature` is
  a POST: if it times out and you retry, you may create a second flag. Before retrying any create,
  re-read with the matching `list_*` and check whether the first attempt landed. PUT updates are
  safe to retry — they set an absolute value, not a delta.
- **No dry run.** There is no preview or validate-only mode. Step 4 is real.
- **Deletes are permanent.** The contract has no restore or undelete operation and publishes no
  retention window. Do not delete to "clean up" a mistake — disable the flag instead.
- **Rate limit: 500 requests/minute** on Management API endpoints, with **no response headers** to
  tell you where you stand and no declared 429. Pace bulk work yourself.
- **Errors are thin.** Failures come back as `{"message": "..."}` with no code to branch on, and 591
  of 615 operations declare no error response at all. Treat any non-2xx as opaque and surface the
  message.
