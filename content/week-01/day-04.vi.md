+++
title = "Ngày 04 - 18/09/2026 (Remote)"
weight = 4
+++

## Việc đã làm

### 1. Bổ sung, chỉnh sửa các diagram cho project_2 PEEP2026

- Use Case Diagram: Bổ sung use case "View Internal Statistics" cho actor Admin 

- Class Diagram: vẽ class diagram cho
  - Web Admin
	- Mobile Application

- Vẽ State Machine Diagram cho:
	- OrderStatus
	- PaymentStatus

### 2. Tìm hiểu các SKILLS đã được tích hợp trong dự án

#### Mục tiêu

Nắm được repo này đã chuẩn hoá những workflow gì, nằm ở đâu, và khi nào nên dùng.

#### Đã tìm hiểu được

Project này có 2 folder chứa skill là: .agents/skills và .claude/skills. Cả 2 đều chứa cùng một nhóm skill chính, nên có thể hiểu là project đang duy trì bộ hướng dẫn cho nhiều agent/context khác nhau.

Các skill được chia theo từng các loại task như sau:

1. `add-backend-endpoint`: được dùng khi cần thêm, mở rộng API backend theo chuẩn NextJS của repo. Bao gồm module, controller, service, DTO, constants, auth và test.
2. `add-env-var`: dùng khi cần thêm biến môi trường cho backend, đảm bảo có validate lúc app boot, có cập nhật .env.example
3. `add-mobile-screen`: dùng khi thêm màn hình ở mobile hoặc thêm API call ở Expo, bám theo convention có sẵn của navigation, theme, i18n và TanStack Query
4. `prisma-migration`: dùng khi sửa schema Prisma hoặc thay đổi database. Skill này nhấn mạnh việc tạo migration incremental, không sửa migration cũ đã commit
5. `production-readiness`: dùng để rà checklist trước khi deploy như là env thật, migration, push notification, bảo mật, CI và verify gate
6. `troubleshoot`: dùng khi gặp lỗi môi trường, lỗi command, lỗi commit hook, lỗi TypeScript, lỗi Auth/IAP hoặc lỗi FCM
7. `write-tests`: dùng khi cần thêm test cho backend hoặc mobile

**Tổng kết**: bộ skill nnay đầy đủ các nhóm việc quan trọng, từ backend, mobile, database migration, env config, test, troubleshoot và readiness trước production.

### 3. Refactor landing page sang kiến trúc component và song ngữ

- Gom các section vào `LandingPage.tsx` — hai route ngôn ngữ dùng chung một giao diện, nhận copy và locale qua props.
- Chuyển 10 component sang nhận nội dung qua props: Hero, Marquee, Highlights, Story, Menu, Stats, Gallery, Testimonials, Visit, Footer. Mỗi component chỉ nhận đúng lát dữ liệu nó cần (kiểu `SiteCopy["hero"]`, `SiteCopy["menu"]`...), nên khi đổi cấu trúc nội dung thì TypeScript báo lỗi ngay tại component liên quan.
- Hai root layout qua route group: `(en)` cho `/` và `(vi)` cho `/vi`. Nhờ vậy mỗi ngôn ngữ có `<html lang>` và metadata riêng — điều không làm được nếu chỉ dùng một layout chung. Font tách ra `fonts.ts` để hai layout dùng chung một instance.
- Khai báo hreflang: cả hai trang đều có canonical riêng và alternate trỏ sang bản còn lại.
- Định dạng giá theo ngôn ngữ: `formatPrice` giờ nhận locale — EN ra 35,000₫, VI ra 35.000₫.
- Dọn dẹp: xoá `mock.ts` (không còn ai import), xoá `layout.tsx`/`page.tsx` cũ, và xoá khối code cũ bị comment trong `Navbar.tsx`.
- Kiểm tra: build thành công, sinh ra 2 route tĩnh `/` và `/vi`; ESLint sạch; xác minh trên dev server: `lang` đúng từng trang, title đúng từng ngôn ngữ, nội dung dịch đúng, nút chuyển EN/VI trỏ đúng chiều, và 164 ảnh trên mỗi route đều trả về 200.
