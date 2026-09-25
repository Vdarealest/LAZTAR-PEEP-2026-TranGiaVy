+++
title = "Ngày 04 - 24/09/2026 (Remote)"
weight = 4
+++

## Thiết kế chi tiết Domain B

### Những gì đã làm hôm nay

- **ERD**: Vẽ `erd_domain_B.puml` bằng PlantUML với quan hệ `warehouses` (1–N) `locations` và self-reference `parent_id`.
- **Data Dictionary**: Mô tả toàn bộ cột của hai bảng (kiểu dữ liệu, nullable, default, khoá, mô tả, ví dụ), kèm các ràng buộc: `UNIQUE (warehouse_id, code)`, `CHECK` cho `location_type` và `purpose`.
- **Business Rules**: Viết 12 rule (BR-B-01 → BR-B-12), ví dụ: chỉ location loại BIN mới được chứa hàng, cấp cha–con phải hợp lệ, không được deactivate location còn tồn kho, hàng QC/DAMAGED không tính vào available, chỉ Admin được tạo/deactivate warehouse.
- **Đồng bộ Primary Key**: Chốt khoá của `warehouses` và `locations` trước 15:00 để Domain D (Inventory) và E (Stock Ledger) tham chiếu.

### Câu hỏi mở cho buổi họp tích hợp (thứ Sáu)

- Location cho hàng đang vận chuyển (in-transit) (với D).
- `max_weight`: chặn hay chỉ cảnh báo (với D, E).
- Khoá location trong lúc kiểm kê (cycle count) (với D).
- Phân quyền theo cấp warehouse hay theo cấp zone (với A).
