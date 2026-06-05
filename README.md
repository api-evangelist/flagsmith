# flagsmith (flagsmith)

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
