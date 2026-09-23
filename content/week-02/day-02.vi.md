+++
title = "Ngày 02 - 22/09/2026 (Remote)"
weight = 2
+++

## Mục tiêu

- Đi sâu vào technical requirements + business requirements.
- Chuyển project brief thành technical design.
- Xác định actors, user flows và system constraints trước khi implementation.

## Những gì đã làm

- Review lại project objective.
- Xác định technical stack và architecture requirements.
- Phân tích warehouse workflow.
- Xác định các actors và responsibilities.
- Phân tích functional requirements.
- Phân tích non-functional requirements.
- Mapping business rules → technical requirements.

## Technical Requirements

- **Backend**: NestJS + TypeScript
- **Database**: PostgreSQL 16
- **ORM**: Prisma
- **Frontend**: React + TypeScript + Next.js
- **Infrastructure**: Docker Compose
- **CI/CD**: GitHub Actions

Hệ thống cần hỗ trợ:

- Transactional operations.
- Complex stock movement.
- Inventory history/audit trail.
- Multi-role access.
- Backend APIs.
- UI cho warehouse staff và managers.

## Main Actors

- **Warehouse Admin** — quản lý master data, warehouse, SKU, bin, users/roles.
- **Warehouse Operator** — receiving, put-away, picking, packing, stock lookup.
- **Inventory Manager / Approver** — approve adjustment và xử lý discrepancy.
- **Supplier** — cung cấp hàng.
- **Customer / Order Holder** — tạo demand/order.
- **Delivery Partner** — vận chuyển hàng.
- **Inventory Ledger Service** — kiểm soát stock movement và audit.

## Functional Requirements

### Inventory & Master Data

- Quản lý warehouse, bin, SKU, product.
- Đảm bảo unit conversion và product data chính xác.

### Inbound

- Receiving hàng.
- Lưu quantity, lot/expiry.
- Update stock thông qua ledger.

### Put-away

- Phân bổ hàng vào storage location.
- Track inventory theo location/lot.

### Allocation

- Dựa trên available stock.
- Áp dụng FEFO.
- Reserved stock không được tính là freely available.

### Picking & Packing

- Picking theo allocated stock.
- Không để xảy ra negative stock.
- Packing phải liên kết với order.

### Delivery & Return

- Quản lý shipment status.
- Xử lý shortage và return.
- Update stock/ledger nhất quán.

### Adjustment

- Inventory adjustment phải có approval.
- Không cho phép unauthorized stock editing.

## Non-functional Requirements

- **Data Integrity**: tồn kho phải chính xác.
- **Transactional Safety**: stock operation phải atomic.
- **Auditability**: mọi inventory change phải có record.
- **Concurrency Control**: tránh race condition và negative stock.
- **Security & Authorization**: phân quyền theo role.
- **Maintainability**: code dễ maintain và phối hợp trong team.

## Kết quả Day 02

Đã chuyển từ việc "hiểu project" sang "hiểu hệ thống cần được xây dựng như thế nào": xác định actors, functional requirements, non-functional requirements và cách business rules ảnh hưởng trực tiếp đến technical design.
