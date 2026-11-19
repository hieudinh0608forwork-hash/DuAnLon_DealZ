# Security, Privacy, Testing & Quality

## Security
HTTPS; least privilege; partner portal not wp-admin; ownership check for every trip/booking/listing/expense; sanitize/validate/escape; prepared SQL; nonce/CSRF protection; rate-limit AI/search; secrets outside Git; restrict CORS; cryptographically verify payment webhooks; audit important state changes; prevent IDOR; validate uploads; escape AI text and never render untrusted HTML.

## Privacy
Minimize collection and retention. Public trip share excludes private profile/contact/payment/booking data unless explicitly authorized. Do not infer financial eligibility from sensitive data.

## Tests
Unit: money/date/commission/state transitions. Integration: repositories/REST permissions/provider/payment adapters. Contract: JSON schemas. E2E: create trip → AI itinerary → edit/save → add service → booking → payment state → dashboard. Security: cross-user/partner isolation, auth/nonce, injection, webhook replay. UI: responsive, keyboard, loading/error/empty. Resilience: provider timeouts, stale availability, duplicate payment events, supplier no response.

## Edge cases
Invalid dates; missing coordinates; malformed AI JSON; unknown place IDs; route provider outage; schedule overlap/impossible travel; budget overrun; listing price changed after quote; availability lost; duplicate checkout; duplicate webhook; partial refund; supplier rejection/no response; revoked share; partner cross-account access.

## Release readiness
No known critical/high security issue; core tests pass; payment sandbox/webhooks tested; backup/restore tested; monitoring/logging configured; API cost/rate limits set; admin runbook and rollback documented.
