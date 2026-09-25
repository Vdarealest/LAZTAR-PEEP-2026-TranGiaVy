+++
title = "Day 03 - 23/09/2026 (On-site)"
weight = 3
+++

## Sprint 0 Kickoff: Task Assignment & Planning

Today the team started Sprint 0: business and database design for the Mini-WMS system.

### 1. General Info

- **Duration**: 23/09/2026 – 28/09/2026
- **Goal**: 5 members split into 5 domains, align on shared conventions, and submit one unified design package (Business Flow, ERD, Data Dictionary, Business Rules).
- **My domain**: B – Warehouse Structure (warehouses, locations)
- **Workspace**: Drive folder `WMS_Sprint0`

### 2. What I did today

- Joined the kickoff meeting; the team agreed on DB conventions: `snake_case` naming, `BIGINT` primary keys, `DECIMAL(18,4)` for quantities, mandatory audit columns, soft delete instead of hard delete.
- Took ownership of Domain B – Warehouse Structure.
- Prepared a shared template doc for the team to fill in Day 1 outputs (domain assignment, conventions, flow draft, table lists, open questions).
- Listed Domain B tables and open questions; proposed the self-referencing `locations` table (Zone → Aisle → Rack → Bin) instead of one table per level, since receiving/staging areas have no aisles or racks.
- Contributed to defining system roles (Admin, Manager, Supervisor, Receiver, Picker, Inspector, Viewer) and their responsibilities; the team agreed on single-level approval for stock adjustments (creator ≠ approver).
- Helped draft the Business Flow: Inbound, Outbound, Transfer, Adjustment, with swimlanes per role.
