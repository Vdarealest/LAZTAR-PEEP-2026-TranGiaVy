+++
title = "Ngày 03 - 30/09/2026 (Remote)"
weight = 3
+++

## Bắt đầu code trang đăng nhập

Bắt đầu implementation dựa trên thiết kế UI hôm qua, mở đầu bằng trang Login.

- Setup module/thư mục `auth` theo convention có sẵn của repo.
- Dựng layout trang Login bằng React/Next.js theo đúng thiết kế đã duyệt: logo, ô email/username, ô password, nút submit, và khu vực hiển thị lỗi.
- Thêm validate form (bắt buộc nhập, đúng định dạng email) trước khi gọi API.
- Kết nối form login với Auth API endpoint có sẵn trong repo, xử lý các trạng thái loading/error/success.
- Lưu auth token trả về và redirect sang Dashboard khi đăng nhập thành công.
- Test luồng đăng nhập trên local với cả thông tin đúng và sai để xác nhận xử lý lỗi hoạt động đúng.
