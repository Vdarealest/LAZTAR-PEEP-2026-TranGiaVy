+++
title = "Ngày 04 - 16/10/2026 (Remote)"
weight = 4
+++

## Responsive

- Kiểm tra toàn bộ các màn hình chính trên 3 breakpoint: mobile, tablet, desktop bằng Chrome DevTools (Toggle device toolbar).
- Sidebar: chuyển sang dạng menu rút gọn (collapsed/hamburger) trên mobile và tablet, thay vì cố định hiển thị đầy đủ như trên desktop.
- Các bảng dữ liệu (Kiểm kê, Sổ cái, Nhà cung cấp, Xuất kho...) bị tràn ngang trên màn hình nhỏ — bọc trong container cuộn ngang riêng (`overflow-x: auto`), không để đẩy vỡ layout trang.
- Dialog thao tác (Khoá tồn, Soạn hàng, Xác nhận xuất, Điều chỉnh nhanh) co lại đúng chiều rộng màn hình trên mobile, nút hành động chuyển sang xếp chồng theo chiều dọc thay vì nằm ngang.
- Dashboard Tổng quan kho: các card/thống kê chuyển từ dạng lưới nhiều cột sang xếp 1 cột trên mobile, biểu đồ co giãn theo chiều rộng khung chứa.
- CapacityPreview (thanh % tải trọng/thể tích) kiểm tra lại hiển thị đúng tỉ lệ trên màn hình hẹp, không bị vỡ số liệu.
- Test lại toàn bộ luồng chính (nhận hàng, xuất hàng, điều chỉnh tồn) trên kích thước mobile thật để đảm bảo thao tác được hết, không có phần tử nào bị che khuất hay không bấm được.
