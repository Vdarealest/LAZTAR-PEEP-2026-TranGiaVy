+++
title = "Tuần 04"
weight = 50
chapter = true
+++

# Tuần 04

**Từ 05/10/2026**

Tiếp tục giai đoạn implementation Mini-WMS, từ module inbound sang Kiểm kê, Sổ cái, Nhà cung cấp, phân quyền thật và Xuất kho:

- Dựng màn hình nhập kho để nhân viên kho ghi nhận hàng nhận từ nhà cung cấp, bao gồm nhập catch weight, validate lot/hạn sử dụng theo FEFO và xử lý chênh lệch.
- Dựng màn Kiểm kê, Sổ cái, Nhà cung cấp, chuyển sang dùng đúng permission matrix từ API thật, và sửa màn Phiếu nhận hàng/Điều chỉnh tồn khớp đúng DTO thật của backend.
- Dựng giao diện Xuất kho ở dạng demo trên dữ liệu giả, kèm form Điều chỉnh nhanh nối API thật.
- Viết lại tính năng Xuất kho để gọi đúng API thật (khoá tồn, soạn hàng, xác nhận xuất) và kiểm tra toàn bộ luồng end-to-end.

## Ghi chú từng ngày

- [Ngày 01 - 05/10/2026 (Remote)](day-01/) — Màn hình nhập kho
- [Ngày 02 - 06/10/2026 (On-site)](day-02/) — Kiểm kê, Sổ cái, Nhà cung cấp, phân quyền thật
- [Ngày 03 - 08/10/2026 (On-site)](day-03/) — Giao diện Xuất kho (demo) + điều chỉnh nhanh tồn kho
- [Ngày 04 - 09/10/2026 (Remote)](day-04/) — Nối giao diện Xuất kho vào API thật
