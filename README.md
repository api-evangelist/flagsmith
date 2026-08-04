# flagsmith (flagsmith)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Flagsmith is an open-source feature flag and remote configuration platform that helps developers manage feature flags across web, mobile, and server-side applications.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/flagsmith/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/flagsmith/refs/heads/main/apis.yml)

## Timestamps

- **Modified:** 2026-05-19

## APIs

### Flagsmith Flags API

The Flagsmith Flags API is the public-facing REST API that client-side and server-side SDKs use to retrieve feature flag values and remote configuration for environments and users. It uses a non-secret Environment Key for authentication and is designed to be fast, scalable, and publicly accessible. The Edge API endpoint at edge.api.flagsmith.com serves requests from AWS Lambda functions running in data centers near the client, providing low-latency global access to flag evaluations.

- **Human URL:** [https://docs.flagsmith.com/clients/rest](https://docs.flagsmith.com/clients/rest)
- **Base URL:** `https://edge.api.flagsmith.com`

#### Tags

- Edge
- Feature Flags
- Flags
- Remote Config
- SDKs

#### Properties

- [Documentation](https://docs.flagsmith.com/clients/rest)
- [OpenAPI](openapi/flagsmith-flags-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/flagsmith-flags-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/flagsmith-flags-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Flagsmith Admin API

The Flagsmith Admin API allows developers to programmatically manage all aspects of their Flagsmith projects. Anything that can be done through the Flagsmith dashboard can also be accomplished via this API, including creating, updating, and deleting projects, environments, feature flags, segments, and users. It uses a secret Organisation API Token for authentication and provides a Swagger interface at api.flagsmith.com/api/v1/docs for interactive exploration.

- **Human URL:** [https://docs.flagsmith.com/integrating-with-flagsmith/flagsmith-api-overview/admin-api](https://docs.flagsmith.com/integrating-with-flagsmith/flagsmith-api-overview/admin-api)
- **Base URL:** `https://api.flagsmith.com/api/v1`

#### Tags

- Administration
- Environments
- Feature Flags
- Projects
- Segments

#### Properties

- [Documentation](https://docs.flagsmith.com/integrating-with-flagsmith/flagsmith-api-overview/admin-api)
- [OpenAPI](openapi/flagsmith-admin-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/flagsmith-admin-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/flagsmith-admin-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [AsyncAPI](asyncapi/flagsmith-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)

## Common Properties

- [GitHub Organization](https://github.com/Flagsmith)
- [LinkedIn](https://www.linkedin.com/company/flagsmith)
- [JSON-LD](json-ld/flagsmith-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [JSON Schema](json-schema/flagsmith-feature-flag-schema.json) — [JSON Schema](https://json-schema.org/specification)
