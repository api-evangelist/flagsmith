---
name: flagsmith-roll-back-a-flag
description: Undo a feature-flag change in Flagsmith — re-publish an earlier version where the
  environment supports it, and fall back to reading the audit log where it does not.
api: Flagsmith Management API
base_url: https://api.flagsmith.com/api/v1
auth: 'Authorization: Api-Key <Master API Key>'
generated: '2026-09-17'
method: generated
source: openapi/_original/flagsmith-api-openapi.json; operationIds grepped from that contract.
  https://docs.flagsmith.com/managing-flags/feature-versioning
operations:
  - get_environment_feature_versions
  - get_environment_feature_version_states
  - publish_environment_feature_version
  - update_environment_feature_state
  - update_feature_state
  - api_v1_projects_audit_list
  - api_v1_audit_retrieve
  - get_feature_lifecycle_counts
---

# Roll back a flag

## Read this first

**What you can undo depends entirely on the environment's `use_v2_feature_versioning` setting, and
Flagsmith publishes no retention window for either path.** Do not promise a caller that a state from
N days ago is still recoverable — the provider does not state that it is.

## If the environment is v2-versioned (`use_v2_feature_versioning: true`)

Versions are immutable and enumerable, so rollback is a first-class operation.

1. `get_environment_feature_versions` (`GET
   /api/v1/environments/{environment_pk}/features/{feature_pk}/versions/`) — list versions. Each
   carries `published`, `is_live`, `live_from`, `created_at`, `created_by` and `published_by`.
2. `get_environment_feature_version_states` on a candidate version to confirm it holds the state you
   want **before** you publish it.
3. `publish_environment_feature_version` (`POST .../versions/{id}/publish/`) — the previously good
   version becomes live again.

This is the only true undo on this API. Prefer it.

## If the environment is not versioned (`use_v2_feature_versioning: false`)

There is no undo. The write was in place and the previous value is gone from the feature state.

1. Read the audit log — `api_v1_projects_audit_list` (`GET /api/v1/projects/{project_pk}/audit/`),
   then `api_v1_audit_retrieve` for the entry — to recover what the value used to be.
2. Set it back by hand with `update_environment_feature_state` (`PUT
   /api/v1/environments/{environment_api_key}/featurestates/{id}/`) or `update_feature_state`.

These are PUTs setting absolute values, so they are safe to retry.

## What has no rollback at all

Deleting a feature, segment, project or environment. Nothing in the 615-operation contract restores
any of them, and no soft-delete or retention window is published. **Treat every DELETE on this API as
permanent** and disable rather than delete when you are unsure.

## Prevention beats rollback

On Enterprise plans, `create_environment_feature_change_request` stages a change for human approval
instead of applying it. For anything an agent is not certain about, a change request is the right
instrument — it is the closest thing this API has to a dry run.

## Rules this API imposes on you

- **No idempotency and no dry run.** `publish_environment_feature_version` is a POST; if it times
  out, re-read the versions list and check `is_live` before retrying.
- **500 requests/minute** on the Management API, with no rate-limit headers and no declared 429.
- Errors are `{"message": "..."}` with no machine-readable code.
