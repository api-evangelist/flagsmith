# Flagsmith

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Flagsmith is an open-source feature flag, remote configuration and experimentation platform built by Bullet Train Ltd. Teams use it to release features safely, run A/B and multivariate tests, and segment users without redeploying code, across web, mobile and server-side applications. It ships as a hosted cloud service on a global low-latency Edge API, as a private cloud deployment, or self-hosted on the customer's own infrastructure, with the core product open source under BSD-3-Clause. Two public API surfaces back it: a non-secret SDK/Flags API for evaluating flags, and a 615-operation Management API that does everything the dashboard does. Flagsmith is OpenFeature compatible, publishes first-party SDKs for thirteen language ecosystems, and operates a remote MCP server exposing 54 tools to AI agents over OAuth.

**Areas:** Feature Flags · Remote Config · Release Management · A/B Testing · Experimentation · Segmentation · Developer Tools · DevOps · Open Source · Software-as-a-Service · MCP · Agent Ready

## Flagsmith on APIs.io

Everything profiled for Flagsmith is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/flagsmith/](https://apis.io/providers/flagsmith/)** — or go straight to one of the APIs or properties below.

### APIs (24)

- [Flagsmith Flags API](https://apis.io/apis/flagsmith/flags-api/) — The Flagsmith Flags API is the public-facing REST API that client-side and server-side SDKs use to retrieve feature flag values and remote configuration for…
- [flagsmith Environments API](https://apis.io/apis/flagsmith/flagsmith-environments-api/) — Manage environments within a project. Environments represent deployment stages such as development, staging, and production.
- [flagsmith Features API](https://apis.io/apis/flagsmith/flagsmith-features-api/) — Manage feature flags within a project. Features can be toggled on or off and can have remote configuration values.
- [flagsmith Identities API](https://apis.io/apis/flagsmith/flagsmith-identities-api/) — Manage user identities within an environment. Identities represent individual users and their associated traits.
- [flagsmith Organisations API](https://apis.io/apis/flagsmith/flagsmith-organisations-api/) — Manage organisations within Flagsmith. Organisations are the top-level container for projects, users, and billing.
- [flagsmith Projects API](https://apis.io/apis/flagsmith/flagsmith-projects-api/) — Manage projects within an organisation. Projects contain environments and feature flags.
- [flagsmith Segments API](https://apis.io/apis/flagsmith/flagsmith-segments-api/) — Manage segments within a project. Segments define groups of users based on traits and rules for targeted flag delivery.
- [flagsmith Users API](https://apis.io/apis/flagsmith/flagsmith-users-api/) — Manage organisation users and their permissions within Flagsmith.
- [flagsmith Webhooks API](https://apis.io/apis/flagsmith/flagsmith-webhooks-api/) — Configure webhooks for environments and organisations to receive notifications about flag changes and audit log events.
- [Flagsmith Admin dashboard API](https://apis.io/apis/flagsmith/flagsmith-admin-dashboard-api/) — Platform hub admin dashboard endpoints.
- [Flagsmith Analytics API](https://apis.io/apis/flagsmith/flagsmith-analytics-api/) — SDK analytics and telemetry.
- [Flagsmith Audit API](https://apis.io/apis/flagsmith/flagsmith-audit-api/) — Access audit logs.
- [Flagsmith Authentication API](https://apis.io/apis/flagsmith/flagsmith-authentication-api/) — Authentication, MFA, OAuth, and token management.
- [Flagsmith Experimental API](https://apis.io/apis/flagsmith/flagsmith-experimental-api/) — Experimental endpoints subject to change.
- [Flagsmith Feature states API](https://apis.io/apis/flagsmith/flagsmith-feature-states-api/) — Manage feature states and feature versioning.
- [Flagsmith Integrations API](https://apis.io/apis/flagsmith/flagsmith-integrations-api/) — Configure third-party integrations (Amplitude, DataDog, Slack, etc.).
- [Flagsmith MCP API](https://apis.io/apis/flagsmith/flagsmith-mcp-api/) — MCP-compatible endpoints.
- [Flagsmith Metadata API](https://apis.io/apis/flagsmith/flagsmith-metadata-api/) — Manage metadata fields and model configuration.
- [Flagsmith O API](https://apis.io/apis/flagsmith/flagsmith-o-api/) — The o API from Flagsmith — 1 operation(s) for o.
- [Flagsmith Onboarding API](https://apis.io/apis/flagsmith/flagsmith-onboarding-api/) — Onboarding flows.
- [Flagsmith Other API](https://apis.io/apis/flagsmith/flagsmith-other-api/) — Other endpoints.
- [Flagsmith Permissions API](https://apis.io/apis/flagsmith/flagsmith-permissions-api/) — Manage user and group permissions across organisations, projects, and environments.
- [Flagsmith Processor API](https://apis.io/apis/flagsmith/flagsmith-processor-api/) — The processor API from Flagsmith — 1 operation(s) for processor.
- [Flagsmith SDK API](https://apis.io/apis/flagsmith/flagsmith-sdk-api/) — SDK endpoints for flags, identities, and traits.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Flagsmith Webhook Events](https://apis.io/asyncapis/flagsmith/flagsmith-webhooks-asyncapi/)

#### Event channels (2)

Individual events and webhooks the provider emits.

- [/environment-webhook](https://apis.io/channels/flagsmith/environment-webhook/)
- [/organisation-webhook](https://apis.io/channels/flagsmith/organisation-webhook/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [flagsmith](https://apis.io/servers/flagsmith/flagsmith/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Flagsmith Agentic Access](https://apis.io/agentic-access/flagsmith/flagsmith-agentic-access/)

#### JSON Schema (1)

The data models the API reads and writes.

- [Flagsmith Feature Flag](https://apis.io/schemas/flagsmith/flagsmith-feature-flag/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Flagsmith Context](https://apis.io/jsonld/flagsmith/flagsmith-context/)

#### Collections (10)

Postman and Open Collection request collections.

- [Flagsmith Admin API](https://apis.io/collections/flagsmith/open-flagsmith-admin-api/)
- [Flagsmith Admin Environments API](https://apis.io/collections/flagsmith/open-flagsmith-environments-api/)
- [Flagsmith Admin Environments Features API](https://apis.io/collections/flagsmith/open-flagsmith-features-api/)
- [Flagsmith Admin Environments Flags API](https://apis.io/collections/flagsmith/open-flagsmith-flags-api/)
- [Flagsmith Admin Environments Identities API](https://apis.io/collections/flagsmith/open-flagsmith-identities-api/)
- [Flagsmith Admin Environments Organisations API](https://apis.io/collections/flagsmith/open-flagsmith-organisations-api/)
- [Flagsmith Admin Environments Projects API](https://apis.io/collections/flagsmith/open-flagsmith-projects-api/)
- [Flagsmith Admin Environments Segments API](https://apis.io/collections/flagsmith/open-flagsmith-segments-api/)
- [Flagsmith Admin Environments Users API](https://apis.io/collections/flagsmith/open-flagsmith-users-api/)
- [Flagsmith Admin Environments Webhooks API](https://apis.io/collections/flagsmith/open-flagsmith-webhooks-api/)

#### Overlays (33)

OpenAPI overlays, including conversational phrasing for each operation.

- [Flagsmith Admin Dashboard Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-admin-dashboard-api-phrasing-overlay/)
- [Flagsmith Analytics Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-analytics-api-phrasing-overlay/)
- [Flagsmith Audit Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-audit-api-phrasing-overlay/)
- [Flagsmith Authentication Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-authentication-api-phrasing-overlay/)
- [Flagsmith Environments Api Overlay](https://apis.io/overlays/flagsmith/flagsmith-environments-api-overlay/)
- [Flagsmith Environments Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-environments-api-phrasing-overlay/)
- [Flagsmith Experimental Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-experimental-api-phrasing-overlay/)
- [Flagsmith Feature States Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-feature-states-api-phrasing-overlay/)
- [Flagsmith Features Api Overlay](https://apis.io/overlays/flagsmith/flagsmith-features-api-overlay/)
- [Flagsmith Features Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-features-api-phrasing-overlay/)
- [Flagsmith Flags Api Overlay](https://apis.io/overlays/flagsmith/flagsmith-flags-api-overlay/)
- [Flagsmith Flags Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-flags-api-phrasing-overlay/)
- [Flagsmith Identities Api Overlay](https://apis.io/overlays/flagsmith/flagsmith-identities-api-overlay/)
- [Flagsmith Identities Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-identities-api-phrasing-overlay/)
- [Flagsmith Integrations Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-integrations-api-phrasing-overlay/)
- [Flagsmith Mcp Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-mcp-api-phrasing-overlay/)
- [Flagsmith Metadata Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-metadata-api-phrasing-overlay/)
- [Flagsmith O Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-o-api-phrasing-overlay/)
- [Flagsmith Onboarding Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-onboarding-api-phrasing-overlay/)
- [Flagsmith Organisations Api Overlay](https://apis.io/overlays/flagsmith/flagsmith-organisations-api-overlay/)
- [Flagsmith Organisations Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-organisations-api-phrasing-overlay/)
- [Flagsmith Other Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-other-api-phrasing-overlay/)
- [Flagsmith Permissions Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-permissions-api-phrasing-overlay/)
- [Flagsmith Processor Api Phrasing Overlay](https://apis.io/overlays/flagsmith/flagsmith-processor-api-phrasing-overlay/)
- [Flagsmith Projects Api Overlay](https://apis.io/overlays/flagsmith/flagsmith-projects-api-overlay/)
- …and 8 more published on APIs.io

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Flagsmith — asyncapi rules](https://apis.io/rules/flagsmith/flagsmith-asyncapi-spectral-rules/)
- [Flagsmith — jsonschema rules](https://apis.io/rules/flagsmith/flagsmith-jsonschema-spectral-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Flagsmith Authentication](https://apis.io/security/flagsmith/flagsmith-authentication/)
- [Flagsmith Domain Security](https://apis.io/security/flagsmith/flagsmith-domain-security/)
- [Flagsmith Trust Center](https://apis.io/security/flagsmith/flagsmith-trust-center/)
- [Flagsmith Vulnerability Disclosure](https://apis.io/security/flagsmith/flagsmith-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Flagsmith Scopes](https://apis.io/scopes/flagsmith/flagsmith-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Flagsmith Plans Pricing](https://apis.io/plans/flagsmith/flagsmith-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Flagsmith Rate Limits](https://apis.io/rate-limits/flagsmith/flagsmith-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Flagsmith Finops](https://apis.io/finops/flagsmith/flagsmith-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://flagsmith.com)
- [Documentation](https://docs.flagsmith.com)
- [Getting started](https://docs.flagsmith.com/getting-started/quick-start)
- [API reference](https://docs.flagsmith.com/integrating-with-flagsmith/flagsmith-api-overview/)
- [Pricing](https://flagsmith.com/pricing)
- [Support](https://docs.flagsmith.com/support/faq)
- [Blog](https://flagsmith.com/blog)
- [Terms of service](https://flagsmith.com/terms-of-service)
- [Privacy policy](https://flagsmith.com/privacy-policy)
- [GitHub](https://github.com/Flagsmith)
- [Status](https://status.flagsmith.com)

## API Evangelist rating

**Kin Score 77.0** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 56.9 |
| Contract governance | 31.8 |
| Operational transparency | 92.1 |
| Developer ergonomics | 79.2 |
| Access clarity | 85.5 |

**Agent readiness 48.3** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 45.1** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/flagsmith/](https://apis.io/providers/flagsmith/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Flagsmith: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/flagsmith/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
