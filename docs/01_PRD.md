# Product Requirements Document

## MVP user outcome
A customer can create a trip, ask AI for destination/itinerary ideas, enter dates/group/interests/budget, see an editable itinerary and map, review estimates, save/reopen/share the trip, browse related services, submit valid booking requests/orders and track status.

## Roles
Guest; Customer; Partner; Operations; Administrator. Partners use a dedicated frontend portal and least-privilege capabilities, not WordPress administrator access.

## Main journeys
### A. AI trip creation
Collect origin, destination or discovery intent, dates, traveler count, budget/currency, interests, pace and transport preferences. Resolve place candidates from trusted sources; generate schema-constrained itinerary; validate; calculate schedule/route/budget deterministically; show assumptions and warnings; user accepts/edits/regenerates.

### B. Manual trip builder
Search/select places, add to days, reorder, edit notes/durations, save. AI is optional.

### C. Save/share
Owner saves trip and creates revocable share link. Permissions: view/comment/edit. Public share must not expose private profile, booking or payment data.

### D. Service booking
Select listing, date/time, quantity/options. Quote from authoritative source. If supplier approval is required, communicate `pending_supplier`; never imply confirmed booking prematurely.

### E. Trip operations
Unified trip view shows itinerary, independent bookings, payment records, expense entries and notifications.

## Functional requirements
- Accounts: register/login/logout/reset/profile/role permissions.
- Discovery: destinations and places, filters and source/update metadata.
- AI planner: structured output, schema validation, warnings; no direct payment or privileged DB writes.
- Itinerary editor: add/remove/reorder/move/edit stops; validate overlaps and travel feasibility.
- Map: stops, route lines, day filters, detail panels; provider adapter replaceable.
- Budget: estimated vs confirmed vs actual, group/per-person totals, categories, deposits and due amounts.
- Services: accommodation, outfit rental, photography, vehicle rental, activities/tickets, tours/guides and approved categories.
- Booking: service-specific fields, supplier, dates, quantity, price/terms snapshots and lifecycle.
- Checkout/payment: adapter; sandbox/manual transfer until credentials exist; server-verified status.
- Partner portal: own listings, price, options, availability and booking requests; moderation workflow.
- Admin: users, partners, places, listings, exceptions, refunds, commissions, content and integrations.
- Notifications: booking/payment/cancellation/supplier response/schedule change.
- Expenses: actual expense records distinct from plan estimates.
- Localization: Vietnamese first, English-ready, VND first.

## Non-functional
Responsive, accessible, secure REST API, server-side validation, caching, graceful provider failure, modular plugin, migrations, backup/restore, pagination and monitoring.

## MVP acceptance
Create/save/reopen trip; valid AI schema; stable or explicitly unresolved place IDs; schedule conflict warnings; budget math matches lines; edit triggers recalculation; share privacy protected; service quote exposes price/availability status; payment verified server-side; cross-user and cross-partner access tests pass.
