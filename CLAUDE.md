# Global instructions for every Claude agent

## Mission
Build DEALZ V2: an AI-assisted travel planner and multi-service booking platform on a fresh WordPress installation.

## Mandatory rules
- Never reuse V1 source code/database/theme/plugins by default.
- Never modify WordPress core.
- Business logic belongs in custom plugin `dealz-core`; theme owns presentation only.
- Use versioned migrations, explicit REST contracts and modular provider adapters.
- Server is authoritative for prices, availability, booking/payment status and totals.
- AI suggests; deterministic code validates. AI must not invent live prices, inventory, booking confirmations or successful payments.
- Validate model output, place IDs, coordinates, dates, time windows and prices server-side.
- Store money as integer minor units (VND đồng integer) or a rigorously defined decimal type; never floating-point totals.
- Use UTC for storage and explicit destination timezone for itinerary display.
- Protect every write with authentication, authorization, validation, sanitization, escaping and appropriate CSRF/nonce controls.
- Use prepared SQL queries, rate limits, idempotency, audit logs and least-privilege capabilities.
- Never commit secrets, `.env`, API keys, payment credentials or privileged tokens.
- Do not fake external integrations. Use clearly labelled mock/sandbox adapters until credentials exist.
- Do not claim a feature works unless tested.
- All screens need loading, empty, error and success states; mobile-first and accessible.

## Multi-agent protocol
- Work only in assigned files/branch.
- Do not edit shared contracts without Architect approval.
- Do not overwrite another agent's work or push directly to main.
- Before coding, list assumptions, dependencies and files to change.
- API/schema change = submit change request; no unilateral changes.
- Small descriptive commits; PR required.
- Each agent must provide `HANDOFF.md`: completed, files changed, contracts used/changed, tests, setup, limitations, next task.

## Definition of done
Acceptance criteria met; tests pass; permissions checked; no secrets/debug leakage; errors/empty states handled; integration compatibility confirmed; limitations documented.
