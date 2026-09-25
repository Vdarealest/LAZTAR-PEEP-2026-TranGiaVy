+++
title = "Ngày 04 - 18/09/2026 (Remote)"
weight = 4
+++

## Việc đã làm

### Refactor landing page sang kiến trúc component và song ngữ

- Gom các section vào `LandingPage.tsx` — hai route ngôn ngữ dùng chung một giao diện, nhận copy và locale qua props.
- Chuyển 10 component sang nhận nội dung qua props: Hero, Marquee, Highlights, Story, Menu, Stats, Gallery, Testimonials, Visit, Footer. Mỗi component chỉ nhận đúng lát dữ liệu nó cần (kiểu `SiteCopy["hero"]`, `SiteCopy["menu"]`...), nên khi đổi cấu trúc nội dung thì TypeScript báo lỗi ngay tại component liên quan.
- Hai root layout qua route group: `(en)` cho `/` và `(vi)` cho `/vi`. Nhờ vậy mỗi ngôn ngữ có `<html lang>` và metadata riêng — điều không làm được nếu chỉ dùng một layout chung. Font tách ra `fonts.ts` để hai layout dùng chung một instance.
- Khai báo hreflang: cả hai trang đều có canonical riêng và alternate trỏ sang bản còn lại.
- Định dạng giá theo ngôn ngữ: `formatPrice` giờ nhận locale — EN ra 35,000₫, VI ra 35.000₫.
- Dọn dẹp: xoá `mock.ts` (không còn ai import), xoá `layout.tsx`/`page.tsx` cũ, và xoá khối code cũ bị comment trong `Navbar.tsx`.
- Kiểm tra: build thành công, sinh ra 2 route tĩnh `/` và `/vi`; ESLint sạch; xác minh trên dev server: `lang` đúng từng trang, title đúng từng ngôn ngữ, nội dung dịch đúng, nút chuyển EN/VI trỏ đúng chiều, và 164 ảnh trên mỗi route đều trả về 200.
