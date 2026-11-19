# REST API Contracts — Draft v1

Namespace `/wp-json/dealz/v1/`. Architect must freeze exact JSON schemas, capabilities, validation, errors and idempotency before frontend implementation.

## Conventions
JSON; UUID domain IDs; ISO-8601 timestamps; money `{amount_minor: 1250000, currency: "VND"}`; paginated collection `{items:[], page:1, per_page:20, total:0}`; errors `{code, message, details}`. Never expose secrets or stack traces.

## Candidate endpoints
Trips: `POST/GET /trips`, `GET/PATCH/DELETE /trips/{id}`, `POST /trips/{id}/duplicate`, `/share`, `/collaborators`.

AI: `POST /ai/trips/generate`, `POST /ai/trips/{id}/replan`. Return preview, warnings and proposed changes; do not persist until user accepts unless autosave is explicitly approved.

Itinerary: `POST /trips/{id}/itinerary/items`, `PATCH/DELETE /trips/{id}/itinerary/items/{item}`, `POST /trips/{id}/itinerary/reorder`, `/validate`.

Places/routes: `GET /places/search`, `GET /places/{id}`, `POST /routes/estimate`.

Budget: `GET /trips/{id}/budget`, `POST /trips/{id}/budget/lines`, `PATCH /budget/lines/{id}`, `POST /trips/{id}/expenses`, `GET /trips/{id}/expenses`.

Services/partners: `GET /services`, `GET /services/{listing}`, `GET /partners/{id}`, `POST/PATCH /partner/listings`, `POST /partner/listings/{id}/availability`.

Booking/payment: `POST /bookings/quote`, `POST /bookings`, `GET /bookings/{id}`, `POST /bookings/{id}/cancel`, `POST /payments/intent`, `POST /payments/webhook/{provider}`.

Account: `GET/PATCH /me`.

For every endpoint define method/path, auth/capability, request/response schema, validation, errors, idempotency, ownership/supplier scoping and whether real/mock/provider-dependent. Frontend must not invent fields.
