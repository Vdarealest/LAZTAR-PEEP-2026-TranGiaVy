+++
title = "Ngày 02 - 14/10/2026 (On-site)"
weight = 2
+++

## Dashboard, phạm vi vai trò, duyệt bút toán đảo, cảnh báo sức chứa

- `feat(dashboard)`: Xây trang Tổng quan kho tự đổi layout theo vai trò đăng nhập.
- `fix(warehouses)`: Kho "đang làm việc" (thanh trên cùng) giờ lọc theo đúng phạm vi vai trò.
- `fix(reversals)`: Quản lý kho (WH_MANAGER) giờ cũng duyệt/từ chối/đảo thẳng được bút toán đảo, không chỉ Admin.
- `feat(warehouses)`: Thêm cảnh báo sức chứa chủ động (CapacityPreview) — hiện thanh % tải trọng/thể tích kho ngay trong dialog Nhận hàng và Nhận hàng chuyển kho, trước khi gửi.
