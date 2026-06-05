# Cvent Registration (cvent-registration)

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
