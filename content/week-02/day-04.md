+++
title = "Day 04 - 24/09/2026 (Remote)"
weight = 4
+++

## Detailed Domain Design – Domain B

### What I did today

- **ERD**: Drew `erd_domain_B.puml` in PlantUML with `warehouses` (1–N) `locations` and the `parent_id` self-reference.
- **Data Dictionary**: Documented all columns of both tables (type, nullability, default, keys, description, example), including constraints: `UNIQUE (warehouse_id, code)`, `CHECK` on `location_type` and `purpose`.
- **Business Rules**: Wrote 12 rules (BR-B-01 → BR-B-12), e.g. only BIN locations can hold stock, valid parent–child levels, no deactivating a location that still has stock, QC/DAMAGED stock excluded from available, only Admin can create/deactivate warehouses.
- **Primary Key Sync**: Finalized `warehouses` and `locations` keys before 15:00 so Domains D (Inventory) and E (Stock Ledger) could reference them.

### Open questions for the integration meeting (Fri)

- In-transit stock location (with D).
- `max_weight`: block vs. warning (with D, E).
- Location lock during cycle count (with D).
- Warehouse-level vs. zone-level permissions (with A).
