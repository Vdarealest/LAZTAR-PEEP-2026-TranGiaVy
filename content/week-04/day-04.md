+++
title = "Day 04 - 09/10/2026 (Remote)"
weight = 4
+++

## Wired the Shipment UI to the Real API

- Read through the full controller/DTO/service (~1000 lines) and the Shipment Prisma schema to understand the real API contract (10 statuses, response field names, the reserve/pick mechanism using cumulative numbers instead of incremental additions).
- Rewrote all the types, service, hooks, and 4 components of the Shipment feature to call the real API instead of mock data.
- The Reserve Stock dialog now uses real FEFO suggestions (the location with the nearest expiry date); the Confirm Shipment dialog correctly looks up the stock row in the STAGING location and prevents duplicate shipment submissions.
- Removed the old mock code; `tsc`/`eslint` run clean.
- Tested the full flow through the real browser (create → reserve → pick → ship) — found the local DB was missing seed data (`movement_types`), re-ran the seed to fix it, retested, and confirmed the full flow works correctly against the real API.
