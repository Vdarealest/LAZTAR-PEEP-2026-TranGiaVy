+++
title = "Ngày 01 - 13/10/2026 (On-site)"
weight = 1
+++

## 1. Module Hàng hoàn trả (Returns) — đã commit

Viết lại hoàn toàn phần FE để khớp đúng API thật, thay vì theo plan ban đầu:

- Dòng hàng trả giờ bắt buộc chọn từ dòng đã xuất thật của 1 đơn xuất (`GET /returns/shipment-sources`), không tự chọn SKU tự do.
- Kiểm định chỉ có 2 hướng xử lý: Nhập lại bán (RESTOCK) hoặc Tiêu huỷ (SCRAP).
- Bước Cân & nhận hàng không tự nhập Lô/Serial/Hạn dùng — bắt buộc khớp đúng dữ liệu lúc xuất.
- Sửa lại phân quyền theo đúng RBAC thật (Quản lý kho được nhận hàng/duyệt, không chỉ Giám sát).

## 2. Nhận hàng đa vị trí (Receipts) — vừa xong, đang chờ commit

Khớp theo API thật "multi-location receive":

- Dựng lại "Cất hàng" (Putaway) — bước bắt buộc thứ 2 sau Nhận hàng mà trước đó đã bị gỡ nhầm (tưởng Nhận hàng đa vị trí thay thế luôn).
- Mỗi dòng hàng tự nhận biết còn nằm ở ô Nhận tạm hay đã vào thẳng Lưu trữ/Hàng hỏng lúc nhận, chỉ hỏi người dùng chọn ô khi thật sự cần cất.
- Chặn cất hàng nếu còn hàng Hư hỏng/Chưa kiểm định ở ô tạm (đúng luật backend).
- Thêm trạng thái "Chưa kiểm định" (SUSPECT) vào lựa chọn tình trạng hàng lúc nhận.
