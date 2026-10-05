+++
title = "Day 01 - 05/10/2026 (Remote)"
weight = 1
+++

## Inbound Receiving Screen

Started the inbound module by building the receiving screen, where warehouse operators record goods arriving from suppliers.

- **Receiving form**: Built the header section (supplier, reference document number, receiving date, warehouse, receiver) and the line items table (SKU, expected quantity, received quantity, lot number, expiry date, storage location).
- **Catch weight handling**: For catch-weight SKUs, the received quantity is entered from the actual weighed value rather than the expected quantity, following the business rule that catch weight must be based on the real weight.
- **Validation**: Added client-side checks before submit: received quantity must be greater than zero, lot and expiry are required for FEFO-tracked SKUs, and expiry must not be in the past. Quantities are formatted to match `DECIMAL(18,4)`.
- **Discrepancy display**: When received quantity differs from expected, the row is highlighted and a reason field appears, so the case can be routed to an approver later.
- Wired the submit action to the receiving API. The screen only sends the receipt; stock is not updated on the frontend, since all stock movement goes through `InventoryLedgerService` on the backend.
- Handled loading, success, and error states, and tested the form with a multi-line receipt, a catch-weight line, and an invalid expiry date.
