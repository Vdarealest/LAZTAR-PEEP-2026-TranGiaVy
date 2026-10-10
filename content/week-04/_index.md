+++
title = "Week 04"
weight = 50
chapter = true
+++

# Week 04

**From 05/10/2026**

Continued the Mini-WMS implementation phase, moving from the inbound module to Cycle Count, Ledger, Suppliers, real role-based permissions, and Shipment:

- Built the receiving screen where warehouse operators record goods arriving from suppliers, including catch-weight entry, FEFO lot/expiry validation, and discrepancy handling.
- Built the Cycle Count, Ledger, and Supplier screens, switched to the real permission matrix from the API, and fixed the Receiving and Adjustment screens to match the backend's real DTOs.
- Built the Shipment screen as a demo on mock data, plus a Quick Adjustment form wired to the real API.
- Rewrote the Shipment feature to call the real Shipment API (reserve, pick, confirm) and verified the full flow end-to-end.

## Daily notes

- [Day 01 - 05/10/2026 (Remote)](day-01/) — Inbound receiving screen
- [Day 02 - 06/10/2026 (On-site)](day-02/) — Cycle Count, Ledger, Suppliers, real permissions
- [Day 03 - 08/10/2026 (On-site)](day-03/) — Shipment UI (demo) + quick inventory adjustment
- [Day 04 - 09/10/2026 (Remote)](day-04/) — Shipment UI wired to the real API
