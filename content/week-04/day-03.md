+++
title = "Day 03 - 08/10/2026 (On-site)"
weight = 3
+++

## Built the Shipment UI (Demo Version) + Quick Inventory Adjustment

- Read and analyzed `plan_week4.md` to lock down the scope: a single Shipment screen covering every role (not split per role), and a Quick Adjustment form on the Inventory page.
- Drew an interactive BPMN-style workflow diagram (illustrative artifact, click each step to see details).
- Wrote the prompt for the AI design tool and reviewed the UI mockup before coding.
- Built the entire Shipment UI: list + detail + 3 action dialogs (Reserve Stock, Pick, Confirm Shipment) — running on in-memory mock data since the backend had no real API yet.
- Found and fixed a bug: the demo data disappeared when navigating from the list to the detail page (because Next.js App Router splits routes into separate JS chunks, each re-initializing its own variables) — fixed by anchoring the shared state on `globalThis`.
- Built the Quick Inventory Adjustment form, wired directly to the real `/api/adjustments` API (already available from last week) — tested creating and cancelling one real adjustment successfully.
- Fixed the Vietnamese term "nhặt hàng" → "soạn hàng" to match `ROLE_LABELS.PICKER` already used in the code.
