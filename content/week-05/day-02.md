+++
title = "Day 02 - 14/10/2026 (On-site)"
weight = 2
+++

## Dashboard, Role-Based Scope, Reversal Approval, Capacity Warnings

- `feat(dashboard)`: Built the Warehouse Overview page, which automatically switches layout based on the logged-in user's role.
- `fix(warehouses)`: The "active" warehouse (top bar) now filters correctly according to role scope.
- `fix(reversals)`: The Warehouse Manager (WH_MANAGER) can now also approve/reject/directly reverse a reversal entry, not just Admin.
- `feat(warehouses)`: Added a proactive capacity warning (CapacityPreview) — shows a weight/volume load percentage bar right inside the Receive and Transfer-Receive dialogs, before submitting.
