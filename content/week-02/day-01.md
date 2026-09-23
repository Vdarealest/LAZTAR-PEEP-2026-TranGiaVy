+++
title = "Day 01 - 21/09/2026 (On-site)"
weight = 1
+++

## Objectives

- Understand the context and business model of Mini-WMS / FreshLink Produce.
- Grasp the end-to-end warehouse workflow.
- Understand the important business rules before starting to code.
- Determine how to organize the 5-person team and the tech stack.

## What I Did

- Researched the purpose of Mini-WMS.
- Analyzed the warehouse workflow: Receiving → Put-away → Allocation → Picking → Packing → Delivery → Return.
- Analyzed the system's 8 business rules.
- Determined the team structure: 2 Backend + 2 Frontend + 1 BA/QA.
- Studied the tech stack: NestJS, PostgreSQL 16, Prisma, React, TypeScript, Next.js, Docker Compose, GitHub Actions.
- Studied the Single Source of Truth principle for stock.

## Knowledge Gained

- This is not a simple CRUD app but a system that simulates real warehouse operations.
- Understood the difference between Physical Inventory and Available Inventory.
- Understood the role of FEFO for fresh goods.
- Understood that Catch Weight must be based on actual quantity/weight.
- Inventory adjustment requires approval.
- Opening balance must avoid duplication.
- Concurrency must be handled to avoid negative stock.

## Most Important Point

`InventoryLedgerService` is where all stock movement is controlled.

Stock must never be updated directly; every inventory change must go through a single unified service to ensure consistency, traceability, and audit history.

## Challenges / Notes

- Business logic is more complex than writing CRUD.
- FEFO, catch weight, and concurrency need special care.
- The team needs clearly divided responsibilities.
- Need to communicate early when blocked.

## Day 01 Result

Gained an overview of the project, the warehouse workflow, the business rules, the team structure, and the technical constraints. The next step is to turn these business rules into concrete technical requirements and architecture.
