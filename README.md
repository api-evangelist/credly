# Credly (credly)

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
