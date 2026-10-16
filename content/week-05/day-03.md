+++
title = "Day 03 - 15/10/2026 (Remote)"
weight = 3
+++

## Fixed Text Overflow Issues

- Reviewed screens where text was overflowing its container: long SKU/product names, multi-level warehouse/location names (Zone → Aisle → Rack → Bin), supplier names, and reason/note fields in dialogs (Adjustment, Return, Reversal).
- Added `truncate` plus a `title` attribute (full text shown on hover) to fixed-width table cells, instead of letting long text push neighboring columns out of shape.
- For columns where the full content needs to stay visible (warehouse address, adjustment reason), switched to multi-line wrapping (`whitespace-normal break-words`) instead of forcing a single line.
- Fixed status badges breaking when the status label was longer than expected — set an appropriate `min-width` and let the text wrap instead of overflowing the badge.
- Fixed the sidebar: long warehouse/user names were breaking the menu layout — added `truncate` with a tooltip, keeping icons fixed instead of getting pushed out of alignment.
- Re-tested with the longest real data available in the DB (longest SKU name, longest warehouse name) to confirm no overflow remained anywhere.
