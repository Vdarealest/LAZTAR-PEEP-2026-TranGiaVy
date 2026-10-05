+++
title = "Ngày 04 - 01/10/2026 (On-site)"
weight = 4
+++

## Quản lý User, Gán quyền & Danh sách Kho

Tiếp tục implementation theo thiết kế UI đã duyệt, xây dựng các màn hình admin cho user, role và warehouse.

- **Quản lý User**: Dựng màn hình danh sách user (tìm kiếm, filter theo status/role, phân trang) và form tạo/sửa user (tên, email, status, warehouse được gán).
- **Gán quyền**: Làm màn hình gán role cho user theo đúng các role đã chốt ở Sprint 0 (Admin, Manager, Supervisor, Receiver, Picker, Inspector, Viewer), kèm bảng ma trận quyền theo từng role.
- **Danh sách Kho**: Dựng màn hình danh sách warehouse (mã, tên, địa chỉ, trạng thái, số lượng location) với action tạo/sửa/deactivate, bám theo các rule BR-B của Domain B (ví dụ chỉ Admin được tạo/deactivate warehouse).
- Kết nối cả 3 màn hình với API endpoint tương ứng, xử lý trạng thái loading/empty/error.
- Test luồng end-to-end: tạo user, gán role, kiểm tra quyền của role đó được áp dụng đúng khi user đăng nhập.
