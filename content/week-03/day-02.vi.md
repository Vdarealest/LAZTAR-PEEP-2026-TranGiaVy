+++
title = "Ngày 02 - 29/09/2026 (On-site)"
weight = 2
+++

## Thiết kế UI

Hôm nay team tập trung thiết kế UI cho hệ thống Mini-WMS.

- Xem lại ERD và business rules đã chốt để xác định các màn hình chính cần có theo từng domain (Warehouse Structure, Inventory, Receiving, Picking/Packing, Adjustment).
- Phác thảo luồng màn hình: Login → Dashboard → danh sách module (Warehouses/Locations, Inventory Lookup, Receiving, Picking, Adjustment).
- Thiết kế layout cho màn hình quản lý Warehouse & Location (danh sách, xem dạng cây theo Zone → Aisle → Rack → Bin, form tạo/sửa).
- Xác định bộ component dùng chung: sidebar navigation, bảng dữ liệu có filter/search, status badge, modal xác nhận, toast thông báo.
- Thống nhất bảng màu, typography và spacing scale để giao diện đồng nhất giữa các màn hình.
- Ghi nhận feedback từ team và chỉnh sửa lại vài màn hình (chuyển bulk action vào toolbar của bảng, đơn giản hoá form tạo location).
