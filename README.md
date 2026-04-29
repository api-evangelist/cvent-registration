# Cvent Registration (cvent-registration)

Cvent Registration is the event registration product within Cvent Event Cloud, delivering online registration websites, attendee data capture, payment processing, registration travel, group registration, custom field collection, and badge / on-site check-in workflows. Registration data is exposed programmatically through the unified Cvent Platform REST API at `api-platform.cvent.com` (OAuth 2.0 client credentials) with a dedicated Registration Guide on the Cvent developer portal. Real-time registration changes are also delivered through Cvent Webhooks.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/cvent-registration/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consuming
- **Access:** 3rd-Party
- **x-type:** company

## Tags

- Attendee Management, Attendees, Conferences, Event Management, Events, OAuth 2.0, On-Site Check-In, Payments, Registration, REST API, Ticketing, Webhooks

## Timestamps

- **Created:** 2024-01-15
- **Modified:** 2026-04-28

## APIs

### Cvent Registration REST API

The registration surface of the unified Cvent Platform REST API. Manage events, registration types, fees, sessions, contacts, attendees, registrations, payments, and travel data. OAuth 2.0 client credentials with the token endpoint at `https://api-platform.cvent.com/ea/oauth2/token`.

- **Human URL:** https://developers.cvent.com/docs/rest-api/guides/registration-guide
- **Base URL:** `https://api-platform.cvent.com`

### Cvent Registration Webhooks

Real-time push notifications for registration, attendee, session, and meeting request events. Subscribers receive payloads at a configured URL for reactive integration with CRM, marketing automation, data warehouses, and analytics.

- **Human URL:** https://developers.cvent.com/docs/webhooks/overview

## Capabilities

- Event creation and lifecycle management
- Attendee and registration record management
- Custom registration field configuration
- Session, fee, and ticket configuration
- Payment processing integration
- On-site check-in and badge workflows
- Real-time event delivery via webhooks

## Use Cases

- Sync event registrations to CRM (Salesforce, Dynamics, HubSpot)
- Stream attendee engagement data to marketing automation
- Drive event registration from corporate portals or microsites
- Reconcile registration fees with finance / ERP systems
- Trigger downstream automation on registration / cancellation

## Common Resources

- [Cvent Online Registration Software](https://www.cvent.com/en/event-management-software/online-registration-software)
- [Developer Portal](https://developers.cvent.com/)
- [API Reference](https://developers.cvent.com/docs/rest-api/reference/reference)
- [Status](https://status.cvent.com/)
- [Support](https://support.cvent.com/)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
