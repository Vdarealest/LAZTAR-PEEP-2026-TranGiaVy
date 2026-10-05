+++
title = "Day 05 - 02/10/2026 (Remote)"
weight = 5
+++

## Location Map, Product Catalog & SKU Detail

Built the screens for the Warehouse Structure and Inventory domains: location visualization, the product catalog, and the SKU detail view.

- **Location Map**: Implemented the location tree/map view (Zone → Aisle → Rack → Bin) from Domain B's self-referencing `locations` table, with status indicators (empty, occupied, over capacity) per bin.
- **Product Catalog**: Built the product list screen (search, filter by category, pagination) with product image, SKU code, unit of measure, and status.
- **SKU Detail**: Built the SKU detail page showing product info, unit conversion, catch weight settings, current stock by location, and lot/expiry information for FEFO-tracked items.
- Linked the Location Map to the SKU Detail page so clicking a bin shows the SKUs currently stored there.
- Connected all three screens to their APIs and verified the data matches what Domain B and D defined (location hierarchy, available vs. reserved stock).
