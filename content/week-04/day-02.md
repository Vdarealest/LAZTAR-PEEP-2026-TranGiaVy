+++
title = "Day 02 - 06/10/2026 (On-site)"
weight = 2
+++

## Cycle Count, Ledger, Suppliers, Real Role-Based Permissions

- Built the Cycle Count screens from scratch: list, detail, session creation, wired to the real API.
- Built the Ledger screen from scratch: view the inventory movement history through the real API.
- Added the Supplier pages (list + detail).
- Switched permissions from a hard-coded matrix to the real permission matrix returned by the API (role-assignment, use-roles).
- Major fixes to the Receiving form and the Inventory Adjustment request screen so they match the backend's actual response/DTO shape.
- Rewrote almost the entire sidebar (`app-sidebar.tsx`, `ui/sidebar.tsx`).
- Added a service to look up stock by storage location (`location-inventory.service.ts`), reused by the Location Map screen.
