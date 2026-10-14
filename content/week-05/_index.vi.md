+++
title = "Tuần 05"
weight = 60
chapter = true
+++

# Tuần 05

**Từ 13/10/2026**

Tiếp tục giai đoạn implementation Mini-WMS, sửa lại các tính năng cho khớp API thật khi backend vừa ship, cùng với sửa dashboard theo vai trò và phạm vi kho:

- Viết lại module Hàng hoàn trả cho khớp đúng dòng hàng trả lấy từ đơn xuất thật, kiểm định RESTOCK/SCRAP và RBAC thật.
- Dựng lại bước Cất hàng cho Nhận hàng đa vị trí, tự nhận biết vị trí theo từng dòng và chặn cất hàng chưa kiểm định/hư hỏng.
- Xây dashboard Tổng quan kho theo vai trò, sửa lọc phạm vi kho, cho Quản lý kho duyệt/đảo bút toán đảo, thêm cảnh báo sức chứa chủ động trong dialog nhận hàng.

## Ghi chú từng ngày

- [Ngày 01 - 13/10/2026 (On-site)](day-01/) — Module Hàng hoàn trả & Nhận hàng đa vị trí/Cất hàng
- [Ngày 02 - 14/10/2026 (On-site)](day-02/) — Dashboard, phạm vi vai trò, duyệt bút toán đảo & cảnh báo sức chứa
