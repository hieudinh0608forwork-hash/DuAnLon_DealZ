# Technical Architecture

## Recommended approach
Fresh WordPress + custom theme + custom plugin `dealz-core` + REST API + modular frontend. WooCommerce may provide suitable cart/order/payment primitives, but do not force time-based availability and supplier confirmation into generic product logic.

**Do not build the whole product as one pasted HTML block.** HTML/CSS/JS is appropriate for frontend components/prototypes; production business logic, authentication, booking, persistence and payments must live in the plugin/backend.

## Boundaries
- Theme: templates, visual system, layout and assets only.
- `dealz-core`: domain model, migrations, repositories, REST, business logic, permissions, integrations, jobs.
- WooCommerce: optional commerce primitives after design approval.
- Frontend: responsive HTML/CSS/JS; build tooling only where it improves maintainability.
- Custom booking domain: service-specific availability, holds, supplier confirmation, snapshots and status.

## Modules
Identity/access; destination/place catalogue; AI orchestration; trip/itinerary; maps/routing; budget/expenses; service catalogue; partner/availability; booking/checkout; payment; notifications; admin/reporting; analytics/audit.

## Suggested plugin structure
`wp-content/plugins/dealz-core/`
- `dealz-core.php`
- `src/Core/`
- `src/Database/`
- `src/Domain/`
- `src/Repositories/`
- `src/Services/`
- `src/REST/`
- `src/Integrations/AI/`
- `src/Integrations/Maps/`
- `src/Integrations/Payments/`
- `src/Jobs/`
- `src/Security/`
- `src/Admin/`
- `tests/`

## Suggested theme
`wp-content/themes/dealz-theme/`: `style.css`, `functions.php` (registration/enqueue only), `theme.json`, `templates/`, `parts/`, `assets/`.

Use Composer/PSR-4 if host supports it; otherwise document a lightweight loader. Never require an unavailable production build step.

## Storage
WordPress users/capabilities for identity. Editorial content as CPT/taxonomies where suitable. Custom tables for relational/high-volume transactional data: trips, itinerary items, availability holds, bookings, ledger. Avoid one giant serialized post-meta blob.

## Provider adapters
AI, geocoding/place search, map renderer, routing, weather, payments, email. MapLibre is a renderer, not a place database or routing engine. Evaluate coverage, licensing, quota and cost for each provider.

## AI flow
Normalize request → retrieve trusted candidates → bounded context → schema-constrained generation → validate output → resolve place IDs/coordinates → deterministic schedule/route/budget checks → preview with confidence/warnings → persist only after user action or approved autosave.

## Environments
Local → staging with mock/sandbox credentials → production with HTTPS, backups, monitoring, restricted admin accounts, secrets outside Git and verified webhooks.
