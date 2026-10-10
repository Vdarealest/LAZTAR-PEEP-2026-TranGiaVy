+++
title = "Ngày 03 - 08/10/2026 (On-site)"
weight = 3
+++

## Dựng giao diện Xuất kho (bản demo) + Điều chỉnh nhanh tồn kho

- Đọc & phân tích `plan_week4.md` để chốt đúng phạm vi: màn Xuất kho (Shipment) gộp mọi vai trò trong 1 màn (không tách riêng từng vai trò), và form Điều chỉnh nhanh tại Tồn kho.
- Vẽ sơ đồ workflow luồng nghiệp vụ dạng BPMN có hiệu ứng tương tác (artifact minh hoạ, nhấn vào từng bước xem chi tiết).
- Viết prompt cho AI thiết kế, duyệt mockup giao diện trước khi code.
- Dựng toàn bộ giao diện Xuất kho: list + chi tiết + 3 dialog thao tác (Khoá tồn, Soạn hàng, Xác nhận xuất) — chạy trên dữ liệu giả lập trong bộ nhớ vì lúc đó backend chưa có API thật.
- Phát hiện và fix bug: dữ liệu demo biến mất khi chuyển từ list sang trang chi tiết (do Next.js App Router tách route thành nhiều JS chunk, mỗi chunk tự khởi tạo lại biến riêng) — fix bằng cách neo state dùng chung vào `globalThis`.
- Dựng form Điều chỉnh nhanh tồn kho, nối thẳng vào API thật `/api/adjustments` (đã có sẵn từ tuần trước) — test tạo và huỷ 1 phiếu thật thành công.
- Sửa thuật ngữ tiếng Việt "nhặt hàng" → "soạn hàng" cho khớp đúng với `ROLE_LABELS.PICKER` đã dùng sẵn trong code.
