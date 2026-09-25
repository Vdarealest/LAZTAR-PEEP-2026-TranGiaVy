+++
title = "Ngày 03 - 23/09/2026 (On-site)"
weight = 3
+++

## Sprint 0 Kickoff: Phân công & Lập kế hoạch

Hôm nay team bắt đầu Sprint 0: thiết kế nghiệp vụ và database cho hệ thống Mini-WMS.

### 1. Thông tin chung

- **Thời gian**: 23/09/2026 – 28/09/2026
- **Mục tiêu**: 5 thành viên chia thành 5 domain, thống nhất convention chung và nộp một bộ thiết kế hợp nhất (Business Flow, ERD, Data Dictionary, Business Rules).
- **Domain của mình**: B – Warehouse Structure (warehouses, locations)
- **Không gian làm việc**: thư mục Drive `WMS_Sprint0`

### 2. Những gì đã làm hôm nay

- Tham gia buổi kickoff; team thống nhất DB convention: đặt tên `snake_case`, primary key `BIGINT`, số lượng dùng `DECIMAL(18,4)`, bắt buộc có audit columns, dùng soft delete thay vì hard delete.
- Nhận phụ trách Domain B – Warehouse Structure.
- Chuẩn bị template doc dùng chung để team điền kết quả Day 1 (phân công domain, convention, bản nháp flow, danh sách bảng, câu hỏi mở).
- Liệt kê các bảng và câu hỏi mở của Domain B; đề xuất bảng `locations` tự tham chiếu (Zone → Aisle → Rack → Bin) thay vì mỗi cấp một bảng, vì khu receiving/staging không có aisle hay rack.
- Góp ý xác định các role của hệ thống (Admin, Manager, Supervisor, Receiver, Picker, Inspector, Viewer) và trách nhiệm từng role; team thống nhất duyệt stock adjustment một cấp (người tạo ≠ người duyệt).
- Hỗ trợ soạn Business Flow: Inbound, Outbound, Transfer, Adjustment, có swimlane theo từng role.
