+++
title = "Day 04 - 16/10/2026 (Remote)"
weight = 4
+++

## Responsive

- Checked all the main screens across 3 breakpoints — mobile, tablet, desktop — using Chrome DevTools (Toggle device toolbar).
- Sidebar: switched to a collapsed/hamburger menu on mobile and tablet, instead of always showing the full expanded version like on desktop.
- Data tables (Cycle Count, Ledger, Suppliers, Shipment, etc.) were overflowing horizontally on small screens — wrapped them in their own horizontally scrollable container (`overflow-x: auto`) instead of letting them break the page layout.
- Action dialogs (Reserve Stock, Pick, Confirm Shipment, Quick Adjustment) now shrink to fit the screen width on mobile, with action buttons stacking vertically instead of sitting side by side.
- Warehouse Overview dashboard: stat cards switched from a multi-column grid to a single column on mobile, with charts resizing to fit their container width.
- Re-checked the CapacityPreview (weight/volume load bar) to confirm it still displays the correct percentage on narrow screens without the numbers breaking.
- Re-tested all the main flows (receiving, shipping, inventory adjustment) on a real mobile viewport to confirm every action is still reachable, with no elements hidden or unclickable.
