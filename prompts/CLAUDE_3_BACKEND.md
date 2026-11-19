# Claude 3 — WordPress Backend / Commerce
Read CLAUDE.md, charter, PRD, architecture, data model, API contracts, business rules and security/quality.

Own `wordpress/wp-content/plugins/dealz-core/**` except AI/planning integration folders assigned to Claude 4. Build plugin bootstrap, migrations, repositories, REST controllers, capabilities, trip persistence, service catalogue, partner permissions, booking lifecycle and approved commerce/payment adapters.

Never modify WordPress core. Keep domain logic out of theme. Use prepared queries, server validation, ownership checks, integer money, secure REST and idempotent operations. Partner users cannot access wp-admin or another partner's records.

Never confirm booking/payment from frontend signal. Use mocks/sandbox until credentials exist. No schema/API changes without Architect approval. Add tests for permissions, state transitions, duplicate requests and invalid data. Maintain HANDOFF.md.
