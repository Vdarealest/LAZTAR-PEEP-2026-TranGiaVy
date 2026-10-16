+++
title = "Ngày 03 - 15/10/2026 (Remote)"
weight = 3
+++

## Xử lý lỗi chữ bị tràn ra ngoài khung

- Rà lại các màn hình bị tràn chữ: tên SKU/sản phẩm dài, tên kho/location nhiều cấp (Zone → Aisle → Rack → Bin), tên nhà cung cấp, và nội dung lý do/ghi chú trong các dialog (Điều chỉnh tồn, Hoàn trả, Đảo bút toán).
- Thêm `truncate` + `title` (tooltip hiện đầy đủ khi hover) cho các ô bảng có độ rộng cố định, thay vì để chữ đẩy vỡ layout cột bên cạnh.
- Với các cột cần xem đầy đủ nội dung (địa chỉ kho, lý do điều chỉnh), chuyển sang cho phép wrap nhiều dòng (`whitespace-normal break-words`) thay vì ép 1 dòng.
- Sửa badge trạng thái (status badge) bị vỡ khi tên trạng thái dài hơn dự kiến — set `min-width` phù hợp và cho chữ tự xuống dòng nếu cần thay vì tràn ra ngoài badge.
- Sửa sidebar: tên warehouse/tên user dài làm vỡ layout menu — thêm `truncate` kèm tooltip, giữ icon cố định không bị đẩy lệch.
- Kiểm tra lại toàn bộ với dữ liệu thật dài nhất có trong DB (tên SKU dài nhất, tên kho dài nhất) để đảm bảo không còn chỗ nào bị tràn.
