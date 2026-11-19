# Initial Task Board

| ID | Priority | Owner | Task | Dependency |
|---|---|---|---|---|
| A-01 | P0 | C1 | Confirm scope and blocking decisions | None |
| A-02 | P0 | C1 | Freeze architecture/module boundaries | A-01 |
| A-03 | P0 | C1 | Freeze schema/migrations contract | A-02 |
| A-04 | P0 | C1 | Freeze REST contracts/JSON schemas | A-03 |
| F-01 | P1 | C2 | Design tokens and responsive shell | A-02 |
| F-02 | P1 | C2 | Landing/discovery UI | F-01 |
| F-03 | P1 | C2 | Trip builder/itinerary editor | A-04 |
| F-04 | P1 | C2 | Map and budget UI | A-04 |
| F-05 | P1 | C2 | Service/checkout/booking UI | A-04 |
| B-01 | P0 | C3 | Plugin scaffold and capabilities | A-02 |
| B-02 | P0 | C3 | Migrations and repositories | A-03 |
| B-03 | P1 | C3 | Trip/itinerary REST API | A-04, B-02 |
| B-04 | P1 | C3 | Service catalogue/partner permissions | A-04 |
| B-05 | P1 | C3 | Booking lifecycle/payment adapter | Rules approved |
| I-01 | P0 | C4 | AI output schema and validator | A-02 |
| I-02 | P1 | C4 | AI trip generation adapter | I-01, A-04 |
| I-03 | P1 | C4 | Budget and schedule engines | Schema v1 |
| I-04 | P1 | C4 | Place/routing adapters | Provider choice |
| I-05 | P1 | C4 | Replanning/service matching | I-02, B-03 |
| Q-01 | P0 | C1 | Contract test suite | A-04 |
| Q-02 | P1 | C1 | E2E/security tests | M2-M4 |
| R-01 | P1 | C1 | Staging/release runbook | MVP modules |

Parallelize only after dependencies/contracts are frozen. Frontend may use exact-schema fixtures; intelligence engines may use approved interfaces but must not create competing APIs/schema.
