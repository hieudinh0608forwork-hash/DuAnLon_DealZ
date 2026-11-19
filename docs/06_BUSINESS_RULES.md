# Business Rules & Financial Model

Labels: **PROPOSED** requires product-owner approval. Historical rules are **LEGACY_CANDIDATE**, not automatic V2 policy.

## Service fulfilment types
- `instant_book`: price and availability checked automatically.
- `supplier_confirmation`: supplier must accept.
- `request_only`: enquiry, not an instant booking.
- `external_affiliate`: redirect; DealZ does not claim to own reservation.

UI/payment flow must match fulfilment type.

## Price breakdown
Base price/unit; quantity/duration; options; known taxes/fees; deposit; discount; total due now; balance later; refundable/non-refundable amounts; currency; quote expiry. Store immutable price/terms snapshot on booking. Label price as live, supplier-confirmed, manually entered or estimated.

## Booking lifecycle (PROPOSED)
Draft → quote → pending_payment or pending_supplier → confirmed → completed. Branches: rejected, cancelled, disputed, refunded, partially_refunded. Never mark confirmed until required supplier/payment conditions are met.

## Multi-service trip
A trip can contain independent bookings with separate suppliers, prices, terms and statuses. Unified trip dashboard is fine; do not imply all services are one atomic reservation.

## Deposits/refunds
Deposit, cancellation window, damage deduction and refund SLA are listing/service-specific and require approval/configuration. Refunds are transactions and status changes, not edits to original totals.

## Budget
Estimated itinerary costs ≠ confirmed booking prices ≠ actual expenses. Group budget sums included lines. Per-person estimate must disclose allocation method. Remaining budget labels its cost basis. Contingency is a planning allowance, not a hidden fee. Never infer financial capability or guarantee affordability.

## Revenue accounting
Track separately: gross booking value, amount collected, refunds, deposit liabilities, supplier payable, commission receivable/earned, payment fees and net platform revenue. Refundable deposits are not revenue. Reverse commission when required by refund/cancellation.

## Partner operations
Proposed onboarding/review, listing moderation, own-data-only access, configurable response deadlines, evidence-based dispute process and reviewed enforcement thresholds.

## Payment safety
Sandbox until credentials/webhooks exist. Verify webhook signature, provider reference, expected amount/currency and order. Idempotent processing. Never trust frontend redirect/query parameter. Reconcile pending payments.

## Legacy candidates
Historical DealZ ideas included service-specific deposits, independent cancellation per service, date changes subject to availability/supplier confirmation and dispute evidence. Revalidate exact rules and thresholds.
