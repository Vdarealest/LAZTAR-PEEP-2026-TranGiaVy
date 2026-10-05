+++
title = "Ngày 01 - 05/10/2026 (Remote)"
weight = 1
+++

## Màn hình nhập kho

Bắt đầu module inbound bằng việc dựng màn hình nhập kho, nơi nhân viên kho ghi nhận hàng nhận từ nhà cung cấp.

- **Form nhập kho**: Dựng phần đầu phiếu (nhà cung cấp, số chứng từ tham chiếu, ngày nhận, warehouse, người nhận) và bảng dòng hàng (SKU, số lượng dự kiến, số lượng thực nhận, số lot, hạn sử dụng, vị trí lưu).
- **Xử lý catch weight**: Với SKU catch weight, số lượng thực nhận được nhập theo khối lượng cân thực tế thay vì số lượng dự kiến, theo business rule catch weight phải dựa trên trọng lượng thực.
- **Validate**: Thêm kiểm tra phía client trước khi submit: số lượng thực nhận phải lớn hơn 0, SKU theo dõi FEFO bắt buộc có lot và hạn sử dụng, hạn sử dụng không được ở quá khứ. Số lượng được định dạng khớp với `DECIMAL(18,4)`.
- **Hiển thị chênh lệch**: Khi số lượng thực nhận khác dự kiến, dòng đó được highlight và hiện ô lý do, để sau này có thể chuyển cho người duyệt xử lý.
- Nối action submit với API nhập kho. Màn hình chỉ gửi phiếu nhận; tồn kho không được cập nhật ở frontend, vì mọi biến động tồn kho đi qua `InventoryLedgerService` ở backend.
- Xử lý các trạng thái loading, thành công và lỗi; test form với phiếu nhiều dòng, một dòng catch weight, và một hạn sử dụng không hợp lệ.
