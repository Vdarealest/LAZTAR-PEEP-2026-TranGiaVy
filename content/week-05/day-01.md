+++
title = "Day 01 - 13/10/2026 (On-site)"
weight = 1
+++

## 1. Returns Module — Committed

Rewrote the entire frontend to match the real API instead of the original plan:

- A return line must now be picked from an actual shipped line of a real shipment (`GET /returns/shipment-sources`), instead of freely selecting any SKU.
- Inspection only has 2 outcomes: Restock (RESTOCK) or Scrap (SCRAP).
- The Weigh & Receive step no longer lets the user freely enter Lot/Serial/Expiry — it must match the data from the original shipment.
- Fixed permissions to match the real RBAC (the Warehouse Manager can receive/approve, not only the Supervisor).

## 2. Multi-Location Receipts — Just Finished, Pending Commit

Matched against the real "multi-location receive" API:

- Rebuilt "Putaway" — the mandatory second step after Receiving that had previously been removed by mistake (assuming multi-location receiving replaced it entirely).
- Each line now detects on its own whether it's still sitting in the Receiving Dock or was placed directly into Storage/Damaged during receiving, only prompting the user to pick a location when putaway is actually needed.
- Blocked putaway when Damaged/Unverified stock remains in the dock location, matching the backend rule.
- Added the "Unverified" (SUSPECT) status to the condition options when receiving goods.
