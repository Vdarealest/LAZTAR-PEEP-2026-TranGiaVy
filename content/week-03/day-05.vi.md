+++
title = "Ngày 05 - 02/10/2026 (Remote)"
weight = 5
+++

## Sơ đồ Vị trí, Danh mục Hàng hóa & Chi tiết SKU

Dựng các màn hình cho domain Warehouse Structure và Inventory: sơ đồ vị trí, danh mục hàng hóa và chi tiết SKU.

- **Sơ đồ Vị trí**: Làm màn hình xem dạng cây/sơ đồ location (Zone → Aisle → Rack → Bin) dựa trên bảng `locations` tự tham chiếu của Domain B, có hiển thị trạng thái từng bin (trống, đã có hàng, vượt sức chứa).
- **Danh mục Hàng hóa**: Dựng màn hình danh sách sản phẩm (tìm kiếm, filter theo category, phân trang) kèm ảnh sản phẩm, mã SKU, đơn vị tính và trạng thái.
- **Chi tiết SKU**: Dựng trang chi tiết SKU hiển thị thông tin sản phẩm, unit conversion, cấu hình catch weight, tồn kho hiện tại theo từng location, và thông tin lot/expiry cho các mặt hàng theo dõi FEFO.
- Liên kết Sơ đồ Vị trí với trang Chi tiết SKU, click vào một bin sẽ hiện các SKU đang được lưu ở đó.
- Kết nối cả 3 màn hình với API tương ứng và xác nhận dữ liệu khớp với những gì Domain B và D đã định nghĩa (cấu trúc location, tồn kho available và reserved).
