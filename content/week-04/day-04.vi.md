+++
title = "Ngày 04 - 09/10/2026 (Remote)"
weight = 4
+++

## Nối giao diện Xuất kho vào API thật

- Đọc toàn bộ controller/DTO/service (~1000 dòng) + schema Prisma của Shipment để nắm đúng hợp đồng API thật (10 trạng thái, tên field response, cơ chế reserve/pick dùng số luỹ kế thay vì cộng dồn).
- Viết lại toàn bộ types, service, hooks và 4 component của tính năng Xuất kho để gọi đúng API thật thay vì dữ liệu giả.
- Dialog Khoá tồn dùng gợi ý FEFO thật (ô hạn dùng gần nhất); dialog Xác nhận xuất tự tra đúng dòng tồn tại ô STAGING và chống bấm xuất trùng.
- Xoá code mock cũ, tsc/eslint chạy sạch.
- Test toàn bộ luồng qua trình duyệt thật (tạo phiếu → khoá tồn → soạn hàng → xuất) — phát hiện DB local thiếu dữ liệu seed (`movement_types`), chạy lại seed để fix, test lại và xác nhận toàn bộ luồng chạy đúng với API thật.
