---
title: "Ngày 03 - 17/09/2026 (Remote)"
weight: 3
---

# Ngày 03 - 17/09/2026 (Remote)

**Báo cáo ngày 03**
Hình thức làm việc: Remote | Dự án: Landing page cafe Hạt Nâu

## A. Công việc thực hành

### 1. Mục tiêu

Hôm nay tôi làm việc remote, xây dựng landing page cho Hạt Nâu — một quán cà phê đặc sản hư cấu tại Quận 3, TP. Hồ Chí Minh. Quán tự rang xay cà phê theo từng mẻ nhỏ và định vị là không gian yên tĩnh để làm việc buổi sáng. Mục tiêu của tôi là biến ý tưởng này thành một landing page responsive, toàn bộ nội dung được dẫn từ dữ liệu mock có kiểu dữ liệu rõ ràng, vừa có thể dùng làm portfolio, vừa đáp ứng yêu cầu bài tập về sử dụng interface và mock data thay vì hardcode nội dung.

### 2. Định nghĩa sản phẩm và lên kế hoạch UI/UX

- Xác định thương hiệu trước khi code: tên, tagline, nhóm khách hàng mục tiêu (khách quen làm việc tại quán, dân văn phòng khu vực, đặt hàng theo lô cho doanh nghiệp) và các điểm bán hàng cần truyền đạt — rang tươi trong ngày, nguồn gốc trực tiếp từ nông trại Cầu Đất, không gian làm việc yên tĩnh và giao hàng nhanh.
- Lên flow trang: hero → băng chạy thông điệp → điểm nổi bật → câu chuyện nguồn gốc → menu → số liệu nổi bật → thư viện ảnh không gian → đánh giá khách hàng → thông tin ghé thăm → footer.
- Chọn phong cách hình ảnh ấm áp, nhẹ nhàng: nền trắng với tông đá và hổ phách, khoảng trắng rộng rãi, card bo góc và viền tinh tế. Ảnh chụp là thứ tạo không khí nên tôi không dùng minh họa trang trí.
- Chọn Playfair Display cho tiêu đề và Be Vietnam Pro cho nội dung, cả hai đều load với subset tiếng Việt để dấu thanh hiển thị đúng.

### 3. Triển khai landing page

- Xây dựng bằng Next.js App Router, React, TypeScript và Tailwind CSS trên nền scaffold create-next-app, dùng pnpm làm package manager. Tôi tự viết icon dạng inline SVG component thay vì thêm thư viện icon để giảm dependency.
- Toàn bộ nội dung được đặt trong file dữ liệu mock có kiểu dữ liệu (`src/data/mock.ts`) với các interface định nghĩa trong `src/types/index.ts`: `MenuItem`, `MenuCategory`, `Highlight`, `Testimonial`, `GalleryImage`, `OpeningHour`, `ContactInfo`, `NavLink`, `FooterLinkGroup` và `SocialLink`. Giá được lưu dạng số và format qua `Intl.NumberFormat("vi-VN")` thay vì viết dạng string.
- Đã triển khai: navigation sticky có mobile menu, hero tối với ảnh tràn ra cạnh phải viewport, băng marquee vô hạn, bốn card điểm nổi bật, phần câu chuyện nguồn gốc, lưới menu, băng số liệu thống kê, mosaic thư viện ảnh, ba đánh giá khách hàng kèm sao, phần ghé thăm với địa chỉ, giờ mở cửa và link liên hệ, cùng footer.
- Xây dựng bộ lọc menu tương tác cho phép chuyển giữa tất cả món, cà phê, đồ uống khác và bánh ngọt. Cùng với mobile menu, đây là hai Client Component duy nhất; các section còn lại giữ nguyên là Server Component vì chỉ render nội dung tĩnh.
- Dùng ảnh remote từ Unsplash và Pravatar qua `next/image`, khai báo cả hai hostname trong `images.remotePatterns` ở `next.config.ts` — nếu không khai báo, Next.js sẽ từ chối render.
- Xử lý accessibility: `aria-label` và `aria-expanded` trên nút toggle menu, alt text mô tả đúng cho mọi ảnh, markup ngữ nghĩa `figure`/`figcaption` và `dl`, `lang="vi"` trên document, và rule `prefers-reduced-motion` để tắt animation marquee.

### 4. Kiểm tra và các vấn đề đã xử lý

- Chạy ESLint, kiểm tra TypeScript qua production build và xác nhận cả hai đều pass sạch.
- Kiểm tra output render từ dev server: mọi section đều có mặt, toàn bộ 174 URL ảnh đã tối ưu trả về HTTP 200 qua `/_next/image`. Tôi không thể chụp screenshot bằng trình duyệt headless vì download bị chặn trên mạng này, nên thay vào đó tôi kiểm tra markup và phản hồi ảnh qua HTTP, đồng thời quan sát rendering trực tiếp trên trình duyệt của mình.
- Ảnh trong menu không khớp với tên món. Tôi chọn ID ảnh Unsplash từ trí nhớ và chỉ kiểm tra URL trả về 200 — chứ không xem ảnh thực sự hiển thị gì. Cà phê sữa đá lại hiển thị một ly cappuccino nóng, trà đào hiển thị một đĩa bánh quy, và một món mặn lại hiển thị nội thất quán cà phê. Tôi sửa bằng cách tải từng ảnh về và kiểm tra trước khi gán, đồng thời đổi tên một món cho khớp với ảnh đã xác minh duy nhất phù hợp. Tôi cũng sửa lại toàn bộ alt text đang mô tả sai ảnh.
- Lưới gallery bị lệch rõ ràng. Ảnh chính dùng tỉ lệ 16:10 trong khi ảnh bên cạnh là hình vuông, tạo ra khoảng trống bên dưới ảnh thấp hơn. Tôi thay bằng mosaic bốn cột, ảnh chính chiếm hai cột hai hàng với chiều cao hàng cố định, tạo thành lưới khít hoàn toàn với năm ảnh, không còn ô trống.
- Trang trông rỗng trên màn hình rộng. Tôi mở rộng container từ `max-w-6xl` lên `max-w-7xl`, cho ảnh hero và gallery chạy tới rìa viewport, thêm băng marquee để phá nhịp — trong khi vẫn giới hạn chiều rộng đoạn văn để độ dài dòng chữ vẫn dễ đọc.
- Vấn đề tooling: lệnh pnpm trên máy này trỏ đến một Corepack shim bị lỗi vì pnpm 12 chuyển sang launcher binary native. Tôi giải quyết bằng `corepack disable` để bản cài đặt đang hoạt động được dùng thay thế.

### 5. Triển khai

- Push project lên GitHub và import vào Vercel với preset Next.js, đặt thư mục gốc của repo làm root directory, sau khi xác nhận lockfile đã được commit và build artifact không bị commit theo.
- Phát hiện GitHub Pages đã được bật trên repo và đang serve một trang Jekyll sinh từ README thay vì ứng dụng. Thay vì chuyển toàn bộ project sang static export — điều này sẽ làm hỏng deployment Vercel vì đổi đường dẫn sub-path và vô hiệu hóa image optimization — tôi làm cấu hình có điều kiện dựa trên biến môi trường `GITHUB_PAGES` chỉ được set bên trong GitHub Actions workflow. Tôi xác minh cả hai chế độ build trên máy local và xác nhận HTML được export áp dụng đúng base path, không chứa lệnh gọi image optimizer.
- Còn lại: chuyển nguồn Pages sang GitHub Actions và push workflow. Link Vercel vẫn là URL chính.

## B. Tổng kết

### Những gì tôi học được

- Xác định thương hiệu và flow các section trước khi code giúp quá trình triển khai nhất quán hơn rất nhiều, và tập trung mọi thứ vào dữ liệu mock có kiểu dữ liệu rõ ràng đồng nghĩa với việc thay đổi nội dung chỉ cần chỉnh một file duy nhất.
- Server Components của Next.js phù hợp cho nội dung tĩnh của landing page, trong khi các phần tương tác như bộ lọc menu và mobile menu cần Client Component — giữ ranh giới này nhỏ thì lượng JavaScript gửi về trình duyệt cũng nhỏ.
- Ảnh remote trong Next.js phải được khai báo trong `next.config.ts` trước khi render được, và HTTP 200 chỉ chứng minh ảnh tồn tại — không đảm bảo ảnh hiển thị đúng nội dung mong muốn.
- Layout trông ổn ở một độ rộng có thể để lộ khoảng trống rõ ràng ở độ rộng khác; row span và chiều cao hàng cố định đáng tin cậy hơn tỉ lệ khung hình khi ghép lưới ảnh.

### Khó khăn và cách giải quyết

- **Ảnh mâu thuẫn với nhãn của chúng**: Tôi ngừng tin vào việc chỉ kiểm tra URL, thay vào đó xem từng ảnh trước khi dùng, rồi điều chỉnh một món trong menu cho khớp với ảnh có thể xác minh được. Alt text được viết lại để mô tả đúng nội dung thực tế — điều quan trọng với người dùng màn hình đọc.
- **Khoảng trống trên màn hình rộng**: Tôi mở rộng container và dùng ảnh full-bleed cùng băng marquee để lấp đầy chiều ngang, trong khi giữ văn bản trong cột hẹp để khả năng đọc không bị ảnh hưởng.
- **Hai môi trường deploy với yêu cầu xung đột**: Vercel serve tại root domain với image optimization, GitHub Pages serve file tĩnh từ sub-path. Cấu hình có điều kiện dựa trên biến môi trường cho phép cả hai hoạt động mà không làm hỏng nhau.

**Link repo:** [https://github.com/Vdarealest/LangdingPage](https://github.com/Vdarealest/LangdingPage)

**URL trang:** [https://landing-page-jade-beta-35.vercel.app/](https://landing-page-jade-beta-35.vercel.app/)