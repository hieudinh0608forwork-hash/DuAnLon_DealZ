# Domain & Data Model (conceptual; Architect must freeze SQL schema)

## Entities
**User/Partner:** WordPress identity + capabilities; partner organization separate from user for future staff accounts.

**Destination:** id, name/slug, country/region, description/media, optional coordinates, tags/status, source, verified_at.

**Place:** id, provider_place_id, destination_id, name/category/address, coordinates, opening-hours data with source/time, visit duration, verification/status.

**Trip:** UUID, owner_user_id, title, origin, destination, dates, timezone, traveler_count, budget_amount_minor, currency, validated preferences, status (draft/active/completed/archived), visibility, timestamps.

**TripCollaborator:** trip_id, user_id/invitation, permission (view/comment/edit), invitation_status.

**ItineraryDay:** id, trip_id, local_date, order, notes.

**ItineraryItem:** id, day_id, optional place_id, title snapshot, local start/end, duration, order, transport mode, notes, estimated_cost_minor, currency, data_status (verified/estimated/user_entered/unresolved), validation flags.

**RouteLeg:** trip_id, from/to item, distance_meters, duration_seconds, mode, provider, calculated_at, status.

**BudgetLine:** trip_id, category, description, quantity, unit/total amount minor, currency, cost_type (estimate/confirmed/actual), source, status.

**Expense:** trip_id, payer, category, amount_minor, currency, date, note, split method.

**Supplier/PartnerListing:** organization and listing separated; listing owner, category, description, location, price basis, options, terms, publication status, verification metadata.

**Availability:** model by inventory quantity/date, time slot/capacity, date range or manual request. Not all services have real-time inventory.

**Booking:** UUID, customer, trip, supplier, listing, service type/date/options snapshot, price/terms snapshots, currency, status, timestamps.

**Payment:** booking/order, provider/reference, amount_minor, currency, status, idempotency key, verified_at. Restrict/redact webhook payloads.

**CommissionLedger:** booking, supplier, gross amount, commission basis points/amount, supplier payable, status (pending/earned/reversed/paid).

**AuditEvent/Notification:** actor, event, target, timestamp, safe metadata and delivery state.

## Rules
Trip has days/items, budget lines, expenses and bookings. Supplier has listings/bookings. Listing has availability. Booking has payments and commission ledger.
Use UUIDs for public IDs; money integer minor units + currency; snapshot price/terms at booking time; retain source/timestamp/confidence for external facts; enforce ownership in service/repository layer.
