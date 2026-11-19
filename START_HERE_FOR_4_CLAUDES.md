# Start Here — 4 Claude accounts

1. Create one private GitHub repository and upload this pack.
2. Save the supplied brand image as `references/brand-reference.png`.
3. Start Claude 1 with `prompts/CLAUDE_1_ARCHITECT_INTEGRATOR.md`.
4. Wait for schema v1, API v1 and task tickets to be frozen.
5. Start Claude 2, 3 and 4 on separate branches with their prompt files.
6. Each agent reads CLAUDE.md + its prompt + only relevant docs/tickets.
7. Each agent commits only to its branch and supplies HANDOFF.md.
8. Claude 1 reviews PRs/contracts/tests and merges.
9. Deploy to staging with mocks/sandbox before production.

Important: Free Claude accounts do not share memory or automatically coordinate. GitHub, versioned docs, branches and PRs are the shared coordination layer.
