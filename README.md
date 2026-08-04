# Credly (credly)

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

Credly is a digital credential and Open Badge platform, owned by Pearson (acquired in 2022, ~$200M), used by more than 2,000 organizations to issue, manage, and verify verifiable digital badges and certifications. The Credly Web Service API (base `https://api.credly.com/v1`, with a sandbox at `https://sandbox-api.credly.com/v1`) lets issuing organizations create and manage badge templates, issue and revoke badges to recipients, read organization and employee data, pull an events feed, and expose recipient credentials via Open Badges Infrastructure (OBI) endpoints. Authentication is HTTP Basic (the organization's `authorization_token` as the username with a blank password) or OAuth 2.0 `client_credentials`. Real-time notifications are delivered via outbound webhooks (HTTPS POST callbacks), not a WebSocket.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/credly/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/credly/refs/heads/main/apis.yml)

## Tags

- Digital Credentials
- Open Badges
- Badging
- Certifications
- Verifiable Credentials
- Pearson

## Timestamps

- **Created:** 2026-07-05
- **Modified:** 2026-07-05

## APIs

### Credly Badge Templates API

List, retrieve, create, update, and delete an organization's badge templates - the reusable credential designs (name, description, image, skills, criteria) that badges are issued against. Templates live under `/v1/organizations/{organization_id}/badge_templates`.

- **Human URL:** [https://www.credly.com/docs/badge_templates](https://www.credly.com/docs/badge_templates)
- **Base URL:** `https://api.credly.com/v1`

#### Tags

- Badge Templates
- Open Badges
- Credentials

#### Properties

- [Documentation](https://docs.credly.com/browse/docs/getting-started)
- [API Reference](https://www.credly.com/docs/badge_templates)
- [OpenAPI](openapi/credly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/credly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/credly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Credly Issued Badges API

Issue badges to recipients from a badge template, list and filter issued badges, retrieve a single badge, replace a badge, and revoke a badge. Issuing takes `recipient_email` and `badge_template_id` (plus optional `issuer_earner_id`, `expires_at`, `locale`, `suppress_badge_notification_email`) under `/v1/organizations/{organization_id}/badges`.

- **Human URL:** [https://www.credly.com/docs/issued_badges](https://www.credly.com/docs/issued_badges)
- **Base URL:** `https://api.credly.com/v1`

#### Tags

- Issued Badges
- Issuing
- Revocation

#### Properties

- [API Reference](https://www.credly.com/docs/issued_badges)
- [OpenAPI](openapi/credly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/credly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/credly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Credly Organizations API

Read organization-level data - organization details and the employees directory (the `workforce` scope). Includes `GET /v1/organizations/{organization_id}/employees` and organization detail lookups used to scope all badge and template operations.

- **Human URL:** [https://docs.credly.com/browse/reference/get_v1-organizations-organization-id-employees](https://docs.credly.com/browse/reference/get_v1-organizations-organization-id-employees)
- **Base URL:** `https://api.credly.com/v1`

#### Tags

- Organizations
- Employees
- Account

#### Properties

- [Documentation](https://docs.credly.com/browse/docs/getting-started)
- [OpenAPI](openapi/credly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/credly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/credly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Credly Events and Webhooks API

Pull a paginated feed of organization events (`badge.created`, `badge.deleted`, `badge.privacy.changed`, `badge.state.changed`) via `GET /v1/organizations/{organization_id}/events`, and receive the same events as outbound webhook callbacks (Credly POSTs a JSON object to a configured HTTPS URL). Delivery is HTTP callback, not WebSocket.

- **Human URL:** [https://www.credly.com/docs/webhooks](https://www.credly.com/docs/webhooks)
- **Base URL:** `https://api.credly.com/v1`

#### Tags

- Events
- Webhooks
- Notifications

#### Properties

- [Documentation](https://www.credly.com/docs/webhooks)
- [API Reference](https://docs.credly.com/browse/reference/get_v1-organizations-organization-id-events)
- [OpenAPI](openapi/credly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/credly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/credly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Credly OBI Recipients API

Open Badges Infrastructure (OBI) specified endpoints that expose a recipient's badge as a public, standards-compliant Open Badges assertion (issuer, badge class, and assertion) so third parties can verify a credential a recipient has earned.

- **Human URL:** [https://www.credly.com/docs/obi_specified_endpoints](https://www.credly.com/docs/obi_specified_endpoints)
- **Base URL:** `https://api.credly.com/v1`

#### Tags

- Recipients
- Open Badges Infrastructure
- Verification

#### Properties

- [Documentation](https://www.credly.com/docs/obi_specified_endpoints)
- [OpenAPI](openapi/credly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/credly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/credly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/credly)
- [Website](https://credly.com)
- [Documentation](https://docs.credly.com/browse/docs/getting-started)
- [Plans](plans/credly-plans-pricing.yml)
- [Rate Limits](rate-limits/credly-rate-limits.yml)
- [Fin Ops](finops/credly-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
