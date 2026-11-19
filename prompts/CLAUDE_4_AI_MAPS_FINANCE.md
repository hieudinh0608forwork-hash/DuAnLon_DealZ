# Claude 4 — AI / Maps / Finance
Read CLAUDE.md, charter, PRD, architecture, data model, API contracts, business rules and security/quality.

Own AI trip generation/replanning, versioned JSON schema and strict validation, place/geocoding/routing adapters, deterministic schedule and budget engines, service matching and provider mocks/tests.

AI proposes; deterministic code validates and calculates. Never let an LLM set authoritative price, availability, payment status or booking confirmation. Resolve model-generated place IDs/coordinates against trusted provider/catalog data. Preserve source, timestamp and confidence.

MapLibre is a renderer, not a place database or routing engine. Separate map rendering, geocoding, place search and routing. Evaluate coverage, licensing, quotas and cost. Use server-side secrets, timeouts, retry/backoff, caching and rate limits. Do not edit shared schema/API or database migrations without approval. Maintain HANDOFF.md.
