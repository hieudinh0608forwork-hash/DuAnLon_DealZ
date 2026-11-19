# Setup & Deployment

## Decisions to record
Hosting; PHP/MySQL; WordPress version; WooCommerce choice; theme/build tooling; AI provider/model; place/map/routing providers; payment gateway; transactional email; domain/staging/production URLs. Do not guess credentials.

## Local setup
Install supported PHP/MySQL/web server; clean WordPress; initialize Git; install `dealz-core` and `dealz-theme`; run migrations and demo seed; configure mock providers; run tests; add WooCommerce only if approved.

## Secret configuration names
`DEALZ_ENV`, `DEALZ_AI_PROVIDER`, `DEALZ_AI_API_KEY`, `DEALZ_MAP_PROVIDER`, `DEALZ_MAP_API_KEY`, `DEALZ_ROUTING_PROVIDER`, `DEALZ_PAYMENT_PROVIDER`, `DEALZ_PAYMENT_SECRET`, `DEALZ_PAYMENT_WEBHOOK_SECRET`, `DEALZ_EMAIL_PROVIDER`, `DEALZ_LOG_LEVEL`. Values stay private; never expose to frontend.

## Deployment
Staging must be clean, HTTPS enabled, backups done, migrations tested, sandbox credentials used, webhooks verified, cron/email tested, roles checked, logs/monitoring available and rollback documented.

Do not go live with mock inventory presented as live, estimated prices presented as guaranteed, or frontend-only payment confirmation.
