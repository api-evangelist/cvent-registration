# Cvent Registration (cvent-registration)

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

Cvent Registration is the event registration product within the Cvent Event Cloud, providing online registration websites, attendee data capture, payment processing, registration travel, group registration, custom field collection, and badge / on-site check-in workflows. Registration data is exposed programmatically through the unified Cvent Platform REST API at api-platform.cvent.com (OAuth 2.0 client credentials), with a dedicated Registration Guide on the Cvent developer portal. Real-time registration changes are also delivered through Cvent Webhooks. Earlier integrations relied on the legacy Cvent SOAP API.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/cvent-registration/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/cvent-registration/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Attendee Management
- Attendees
- Conferences
- Event Management
- Events
- OAuth 2.0
- On-Site Check-In
- Payments
- Registration
- REST API
- Ticketing
- Webhooks

## Timestamps

- **Created:** 2024-01-15
- **Modified:** 2026-04-28

## APIs

### Cvent Registration REST API

The Cvent Registration REST API is the registration surface of the unified Cvent Platform REST API. It allows integrations to create and manage events, registration types, fees, sessions, contacts, attendees, registrations, payments, and travel data. Authentication uses OAuth 2.0 client credentials with the token endpoint at api-platform.cvent.com/ea/oauth2/token. Detailed registration workflows are documented in the Registration Guide.

- **Human URL:** [https://developers.cvent.com/docs/rest-api/guides/registration-guide](https://developers.cvent.com/docs/rest-api/guides/registration-guide)
- **Base URL:** `https://api-platform.cvent.com`

#### Tags

- Attendees
- Contacts
- Events
- OAuth 2.0
- Payments
- Registration
- REST
- Sessions
- Ticketing

#### Properties

- [Documentation](https://developers.cvent.com/docs/rest-api/overview)
- [Registration Guide](https://developers.cvent.com/docs/rest-api/guides/registration-guide)
- [API Reference](https://developers.cvent.com/docs/rest-api/reference/reference)
- [Authentication](https://developers.cvent.com/docs/rest-api/explanation/authentication)
- [O Auth Token Endpoint](https://api-platform.cvent.com/ea/oauth2/token)
- [Changelog](https://developers.cvent.com/docs/rest-api/changelog)
- [Postman Collection](collections/cvent-registration.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cvent-registration.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Cvent Registration Webhooks

Cvent Webhooks deliver real-time push notifications when registration, attendee, session, and meeting request events occur in Cvent. Webhook subscribers receive event payloads at a configured URL, enabling reactive integration with CRM, marketing automation, data warehouses, and analytics without polling the REST API.

- **Human URL:** [https://developers.cvent.com/docs/webhooks/overview](https://developers.cvent.com/docs/webhooks/overview)

#### Tags

- Attendees
- Events
- Notifications
- Real-Time
- Registration
- Webhooks

#### Properties

- [Documentation](https://developers.cvent.com/docs/webhooks/overview)
- [Getting Started](https://developers.cvent.com/docs/webhooks/tutorials/account-setup)
- [Guide](https://developers.cvent.com/docs/webhooks/understanding-webhooks)
- [Technical Requirements](https://developers.cvent.com/docs/webhooks/technical-requirements)
- [Postman Collection](collections/cvent-registration.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/cvent-registration.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/cvent)
- [Website](https://www.cvent.com/en/event-management-software/online-registration-software)
- [Developer Portal](https://developers.cvent.com/)
- [API Reference](https://developers.cvent.com/docs/rest-api/reference/reference)
- [Authentication](https://developers.cvent.com/docs/rest-api/explanation/authentication)
- [O Auth Token Endpoint](https://api-platform.cvent.com/ea/oauth2/token)
- [Status Page](https://status.cvent.com/)
- [Support](https://support.cvent.com/)
- [Pricing](https://www.cvent.com/en/pricing)
- [Terms of Service](https://www.cvent.com/en/terms-of-service)
- [Privacy Policy](https://www.cvent.com/en/privacy-policy)
- [Twitter](https://twitter.com/cvent)
- [LinkedIn](https://www.linkedin.com/company/cvent/)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
