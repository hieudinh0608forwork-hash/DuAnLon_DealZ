# Four-Agent Work Plan

## Operating model
One shared GitHub repository; one branch per Claude account. Claude 1 owns integration and shared contracts. GitHub is the coordination memory; Claude accounts do not share chat memory.

## Claude 1 — Architect / Integrator / QA
Branch `agent/architect`. Owns scope clarification, architecture, domain model, API contracts, ticketing, contract tests, integration, review, E2E/security tests and release runbook. Does not implement other modules wholesale.

## Claude 2 — Frontend / UX
Branch `agent/frontend`. Owns custom theme and frontend: landing/discovery, trip brief, itinerary editor, map UI, budget dashboard, customer trip dashboard, service/checkout/booking screens, partner portal UI shell. Uses fixtures matching approved API contracts. No backend/schema edits.

## Claude 3 — WordPress Backend / Commerce
Branch `agent/backend`. Owns `dealz-core` bootstrap, migrations/repositories, REST/auth/capabilities, trip persistence, service catalogue, partner permissions, booking lifecycle, approved WooCommerce/payment adapter and admin operations. No AI engine internals.

## Claude 4 — AI / Maps / Finance
Branch `agent/intelligence`. Owns AI orchestration, prompts/schema validation, place/geocoding/routing adapters, deterministic schedule/budget engines, replanning, service matching and provider mocks. No unilateral core schema/REST changes.

## Shared file ownership
`docs/**`: Claude 1 only. Database/migrations and REST: Claude 3 after Architect schema freeze. AI/maps/planning integrations: Claude 4. Theme/frontend: Claude 2. Contract tests: Claude 1; module tests in each agent's folder.

## Milestones
M0 specification freeze: Architect publishes approved schema/API/tickets.
M1 foundation: backend scaffold/roles; frontend design tokens/shell; AI provider interfaces/schema; Architect CI/contracts.
M2 trip core: trip CRUD; builder/editor; AI generation + validation; E2E integration.
M3 maps/budget: route/place adapters; map UI; persistence/endpoints; provider failure tests.
M4 marketplace/booking: service/partner/booking/payment; service/checkout UI; matching/quote checks; webhook/idempotency tests.
M5 hardening: regression, security, deployment, release.

## Git protocol
No direct main pushes. Pull latest main before task. Small commits. PR summary includes files/tests/screenshots. Claude 1 merges after review. File owner resolves conflicts; never force-push over another agent.

## Ticket template
ID; Goal; User value; Scope; Allowed files; Forbidden files; Dependencies; Contract version; Acceptance criteria; Test commands; Deliverable.
