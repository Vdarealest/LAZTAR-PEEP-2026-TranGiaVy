+++
title = "Ngày 01 - 21/09/2026 (On-site)"
weight = 1
+++

## Mục tiêu

- Hiểu context và business model của Mini-WMS / FreshLink Produce.
- Nắm được workflow kho từ đầu đến cuối.
- Hiểu các business rules quan trọng trước khi bắt đầu code.
- Xác định cách tổ chức team 5 người và tech stack.

## Những gì đã làm

- Tìm hiểu mục đích của Mini-WMS.
- Phân tích warehouse workflow: Receiving → Put-away → Allocation → Picking → Packing → Delivery → Return.
- Phân tích 8 business rules của hệ thống.
- Xác định team structure: 2 Backend + 2 Frontend + 1 BA/QA.
- Tìm hiểu tech stack: NestJS, PostgreSQL 16, Prisma, React, TypeScript, Next.js, Docker Compose, GitHub Actions.
- Tìm hiểu nguyên tắc Single Source of Truth đối với stock.

## Kiến thức đạt được

- Đây không phải CRUD app đơn giản mà là hệ thống mô phỏng nghiệp vụ kho thực tế.
- Hiểu được sự khác nhau giữa Physical Inventory và Available Inventory.
- Hiểu vai trò của FEFO đối với hàng tươi.
- Hiểu Catch Weight phải dựa trên quantity/weight thực tế.
- Inventory adjustment cần approval.
- Opening balance phải tránh duplicate.
- Cần xử lý concurrency để tránh negative stock.

## Điểm quan trọng nhất

`InventoryLedgerService` là nơi kiểm soát toàn bộ stock movement.

Không được update stock trực tiếp; mọi thay đổi tồn kho phải đi qua một service thống nhất để đảm bảo consistency, traceability và audit history.

## Khó khăn / lưu ý

- Business logic phức tạp hơn việc viết CRUD.
- FEFO, catch weight và concurrency cần đặc biệt cẩn thận.
- Team cần phân chia responsibility rõ ràng.
- Khi bị block cần communicate sớm.

## Kết quả Day 01

Đã có cái nhìn tổng quan về project, warehouse workflow, business rules, team structure và technical constraints. Bước tiếp theo là chuyển các business rules này thành technical requirements và architecture cụ thể.
