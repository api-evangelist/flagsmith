# Flagsmith (flagsmith)
Flagsmith is a feature flag and remote configuration platform that enables teams to manage feature releases, A/B tests, and application configuration across web, mobile, and server-side applications. Their developer platform provides both a public-facing Edge API for low-latency flag evaluation and an Admin API for programmatic management of projects, environments, segments, and feature flags.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/flagsmith/refs/heads/main/apis.yml)

## Scope

- **Type:** Contract
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags:

 - Feature Flags, Remote Config, SDKs, Administration, Segments

## Timestamps

- **Created:** 2026-03-20
- **Modified:** 2026-03-20

## APIs

### Flagsmith Flags API
The Flagsmith Flags API is the public-facing REST API that client-side and server-side SDKs use to retrieve feature flag values and remote configuration for environments and users. It uses a non-secret Environment Key for authentication and is designed to be fast, scalable, and publicly accessible. The Edge API endpoint at edge.api.flagsmith.com serves requests from AWS Lambda functions running in data centers near the client, providing low-latency global access to flag evaluations.

**Human URL:** [https://docs.flagsmith.com/clients/rest](https://docs.flagsmith.com/clients/rest)


#### Tags:

 - Feature Flags, Remote Config, Flags, SDKs, Edge

#### Properties

- [Documentation](https://docs.flagsmith.com/clients/rest)
- [OpenAPI](openapi/flagsmith-flags-api-openapi.yml)

### Flagsmith Admin API
The Flagsmith Admin API allows developers to programmatically manage all aspects of their Flagsmith projects. Anything that can be done through the Flagsmith dashboard can also be accomplished via this API, including creating, updating, and deleting projects, environments, feature flags, segments, and users. It uses a secret Organisation API Token for authentication and provides a Swagger interface at api.flagsmith.com/api/v1/docs for interactive exploration.

**Human URL:** [https://docs.flagsmith.com/integrating-with-flagsmith/flagsmith-api-overview/admin-api](https://docs.flagsmith.com/integrating-with-flagsmith/flagsmith-api-overview/admin-api)


#### Tags:

 - Feature Flags, Administration, Projects, Environments, Segments

#### Properties

- [Documentation](https://docs.flagsmith.com/integrating-with-flagsmith/flagsmith-api-overview/admin-api)
- [OpenAPI](openapi/flagsmith-admin-api-openapi.yml)
- [AsyncAPI](asyncapi/flagsmith-webhooks-asyncapi.yml)

## Common Properties

- [Portal](https://docs.flagsmith.com/)
- [Documentation](https://docs.flagsmith.com/docs)
- [Website](https://flagsmith.com/)
- [PrivacyPolicy](https://flagsmith.com/privacy-policy)
- [TermsOfService](https://flagsmith.com/terms-of-service)
- [Blog](https://flagsmith.com/blog)
- [Login](https://app.flagsmith.com/)

## Maintainers

**FN:** API Evangelist

**Email:** info@apievangelist.com
