+++
title = "Day 02 - 22/09/2026 (Remote)"
weight = 2
+++

## Objectives

- Dive deeper into the technical requirements and business requirements.
- Turn the project brief into a technical design.
- Determine actors, user flows, and system constraints before implementation.

## What I Did

- Reviewed the project objective again.
- Determined the technical stack and architecture requirements.
- Analyzed the warehouse workflow.
- Identified the actors and their responsibilities.
- Analyzed functional requirements.
- Analyzed non-functional requirements.
- Mapped business rules to technical requirements.

## Technical Requirements

- **Backend**: NestJS + TypeScript
- **Database**: PostgreSQL 16
- **ORM**: Prisma
- **Frontend**: React + TypeScript + Next.js
- **Infrastructure**: Docker Compose
- **CI/CD**: GitHub Actions

The system needs to support:

- Transactional operations.
- Complex stock movement.
- Inventory history/audit trail.
- Multi-role access.
- Backend APIs.
- UI for warehouse staff and managers.

## Main Actors

- **Warehouse Admin** — manages master data, warehouses, SKUs, bins, users/roles.
- **Warehouse Operator** — receiving, put-away, picking, packing, stock lookup.
- **Inventory Manager / Approver** — approves adjustments and handles discrepancies.
- **Supplier** — supplies goods.
- **Customer / Order Holder** — creates demand/orders.
- **Delivery Partner** — ships goods.
- **Inventory Ledger Service** — controls stock movement and auditing.

## Functional Requirements

### Inventory & Master Data

- Manage warehouses, bins, SKUs, and products.
- Ensure accurate unit conversion and product data.

### Inbound

- Receive goods.
- Store quantity, lot/expiry.
- Update stock through the ledger.

### Put-away

- Allocate goods to storage locations.
- Track inventory by location/lot.

### Allocation

- Based on available stock.
- Apply FEFO.
- Reserved stock must not be counted as freely available.

### Picking & Packing

- Pick according to allocated stock.
- Prevent negative stock from occurring.
- Packing must be linked to the order.

### Delivery & Return

- Manage shipment status.
- Handle shortages and returns.
- Update stock/ledger consistently.

### Adjustment

- Inventory adjustment must have approval.
- Unauthorized stock editing is not allowed.

## Non-functional Requirements

- **Data Integrity**: inventory must be accurate.
- **Transactional Safety**: stock operations must be atomic.
- **Auditability**: every inventory change must have a record.
- **Concurrency Control**: avoid race conditions and negative stock.
- **Security & Authorization**: role-based access control.
- **Maintainability**: code must be easy to maintain and for the team to collaborate on.

## Day 02 Result

Moved from "understanding the project" to "understanding how the system needs to be built": identified actors, functional requirements, non-functional requirements, and how the business rules directly influence the technical design.
