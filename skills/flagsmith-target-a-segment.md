---
name: flagsmith-target-a-segment
description: Define an audience in a Flagsmith project and override a feature's value for that
  audience in one environment.
api: Flagsmith Management API
base_url: https://api.flagsmith.com/api/v1
auth: 'Authorization: Api-Key <Master API Key>'
generated: '2026-09-17'
method: generated
source: openapi/_original/flagsmith-api-openapi.json; operationIds grepped from that contract.
  https://docs.flagsmith.com/basic-features/managing-segments
operations:
  - list_project_segments
  - create_project_segment
  - get_project_segment
  - update_project_segment
  - create_segment_override
  - list_feature_segments
  - delete_feature_segment
---

# Target a segment

## The shape

A **Segment** is a named audience owned by a **project**, defined by nested rule groups
(`SegmentRule`, type ALL / ANY / NONE) each holding `Condition` rows of `{property, operator,
value}`. A **segment override** is a `FeatureState` bound to that segment inside **one environment**.
Segments are project-scoped; overrides are environment-scoped. That asymmetry is the point — you
define the audience once and roll it out one environment at a time.

## Steps

1. **Check for an existing segment.** `list_project_segments` (`GET
   /api/v1/projects/{project_pk}/segments/`). Reuse before you create — there is a hard limit of
   **500 segments per project**.

2. **Create the segment.** `create_project_segment` (`POST
   /api/v1/projects/{project_pk}/segments/`) with `name`, `description` and `rules`. Conditions are
   evaluated against identity **traits**, so the property names must match the trait keys your SDKs
   actually set. Limits: **100 conditions** per segment rule; a segment rule value is capped at
   **1,000 bytes**.

3. **Override the feature for that segment.** `create_segment_override` (`POST
   /api/v1/environments/{environment_api_key}/features/{feature_pk}/create-segment-override/`). This
   sets the segment binding and its value in a single call — use it rather than assembling the
   feature-segment and the feature-state separately.

   This operation applies to environments **without** v2 feature versioning. In a v2-versioned
   environment, set the segment-scoped state inside a version
   (`create_environment_feature_version_state`) and publish it.

4. **Verify.** `list_feature_segments` (`GET /api/v1/features/feature-segments/`) filtered to the
   feature and environment.

5. **Remove it when done.** `delete_feature_segment` (`DELETE
   /api/v1/features/feature-segments/{id}/`) removes the override. This is the one clean reversal in
   this flow — it deletes the override and the feature falls back to the environment default. It
   does not delete the segment.

## Precedence — what actually gets served

For a given identity, a per-identity override beats a segment override, and a segment override beats
the environment default. Where several segments match, the highest-priority segment wins. If a flag
is not behaving as you expect, check for a per-identity override before you touch the segment.

## Rules this API imposes on you

- **2,000 segment overrides per environment** is a hard limit.
- **No idempotency**: `create_project_segment` and `create_segment_override` are POSTs with no
  dedupe. Re-read with `list_project_segments` / `list_feature_segments` before retrying.
- **500 requests/minute** on the Management API, with no rate-limit response headers.
- Deleting a **segment** has no undo. Deleting an **override** is safe and expected.
