---
title: "Thứ 4"
weight: 3
---

# Ngày: Thứ 4

## Công việc đã làm

- Ôn tập lý thuyết React cơ bản (component, props, state, Virtual DOM, hooks...).
- Tìm hiểu và so sánh React với Next.js.
- Tìm hiểu các khái niệm cốt lõi của Next.js (App Router, SSR/SSG/ISR, API Routes...).

## A. Lý Thuyết

### Phần 1. React cơ bản

**1. React là gì?**

React là một thư viện JavaScript (do Meta/Facebook phát triển) dùng để xây dựng giao diện người dùng (UI), đặc biệt cho các ứng dụng dạng Single Page Application (SPA). React tập trung vào việc xây dựng UI theo hướng component, tái sử dụng được, và cập nhật giao diện hiệu quả nhờ Virtual DOM.

**2. Component trong React là gì? Có mấy loại component?**

Component là một khối UI độc lập, có thể tái sử dụng, nhận đầu vào (props) và trả về giao diện (JSX). Có 2 loại chính:

- **Function Component**: viết dưới dạng hàm JavaScript, dùng Hooks để quản lý state/lifecycle (phổ biến hiện nay).
- **Class Component**: viết dưới dạng class kế thừa `React.Component`, có state và lifecycle methods riêng (ít dùng trong code mới).

**3. JSX là gì?**

JSX (JavaScript XML) là cú pháp mở rộng cho phép viết code giống HTML trực tiếp trong JavaScript. JSX được biên dịch (qua Babel) thành các lệnh gọi `React.createElement()` để tạo ra Virtual DOM.

**4. Props là gì?**

Props (properties) là dữ liệu được truyền từ component cha xuống component con. Props chỉ đọc (read-only) — component con không được tự ý thay đổi props nhận vào.

**5. State là gì? State khác Props như thế nào?**

State là dữ liệu nội bộ của component, có thể thay đổi theo thời gian; khi thay đổi sẽ khiến component re-render.

Khác biệt: Props được truyền từ ngoài vào (cha → con) và không thể bị con thay đổi; State được quản lý bên trong chính component đó và được cập nhật bằng các hàm như `setState`/`useState`.

**6. Virtual DOM là gì? Vì sao React sử dụng Virtual DOM?**

Virtual DOM là một bản sao nhẹ (in-memory) của DOM thật, được React dùng để so sánh (diffing) giữa trạng thái cũ và mới trước khi cập nhật DOM thật. React dùng Virtual DOM vì thao tác trực tiếp trên DOM thật rất tốn kém; nhờ diffing + reconciliation, React chỉ cập nhật đúng phần thực sự thay đổi, giúp tăng hiệu năng.

**7. Hooks là gì? Kể tên một số Hook phổ biến trong React.**

Hooks là các hàm đặc biệt cho phép function component sử dụng state, lifecycle và các tính năng khác của React mà không cần viết class. Một số hook phổ biến: `useState`, `useEffect`, `useContext`, `useRef`, `useMemo`, `useCallback`, `useReducer`.

**8. useState dùng để làm gì?**

`useState` dùng để khai báo và quản lý state trong function component. Nó trả về một cặp `[giá trị state, hàm cập nhật state]`; mỗi lần gọi hàm cập nhật sẽ khiến component re-render với giá trị mới.

**9. useEffect dùng để làm gì?**

`useEffect` dùng để thực hiện các side effect (tác vụ phụ) trong component như gọi API, đăng ký/hủy sự kiện, thao tác DOM, cập nhật title... Nó chạy sau khi component render, có thể cấu hình chạy lại theo dependency array, và có thể trả về hàm cleanup để dọn dẹp khi component unmount hoặc trước khi effect chạy lại lần sau.

**10. Lifecycle của một React Component gồm những giai đoạn nào?**

Gồm 3 giai đoạn chính:

- **Mounting**: component được tạo và gắn vào DOM lần đầu.
- **Updating**: component re-render khi props/state thay đổi.
- **Unmounting**: component bị gỡ khỏi DOM.

Ở class component tương ứng với các method như `componentDidMount`, `componentDidUpdate`, `componentWillUnmount`; ở function component được mô phỏng bằng `useEffect` với dependency array khác nhau.

**11. Client-Side Rendering (CSR) là gì?**

CSR là cách render trong đó trình duyệt tải về một file HTML gần như rỗng cùng một bundle JavaScript; JavaScript sau đó chạy trên trình duyệt (client) để dựng nên toàn bộ giao diện. Đây là cách render mặc định của React thuần (ví dụ Create React App).

**12. React Router là gì?**

React Router là thư viện bên thứ ba giúp quản lý routing (điều hướng giữa các trang/URL) trong ứng dụng React thuần, vì bản thân React không có tính năng routing tích hợp sẵn.

**13. React thuần có hỗ trợ Routing, SEO và API Server không?**

Không. React thuần chỉ là thư viện UI: không có routing tích hợp (cần cài React Router), không tối ưu SEO sẵn (vì render phía client nên HTML ban đầu gần như rỗng), và không có khả năng viết API server tích hợp (cần backend riêng như Node/Express).

**14. Context API là gì? Khi nào nên sử dụng?**

Context API là cơ chế của React giúp chia sẻ dữ liệu (state) xuyên suốt cây component mà không cần truyền props qua từng cấp trung gian (tránh "prop drilling"). Nên dùng khi có dữ liệu toàn cục cần nhiều component ở các cấp khác nhau sử dụng, ví dụ: theme, thông tin user đăng nhập, ngôn ngữ.

**15. SPA (Single Page Application) là gì?**

SPA là ứng dụng web chỉ tải một trang HTML duy nhất, sau đó dùng JavaScript để cập nhật động nội dung khi người dùng điều hướng, không cần tải lại toàn bộ trang. Giúp trải nghiệm mượt hơn nhưng cần xử lý riêng vấn đề SEO và tốc độ tải trang lần đầu.

### Phần 2. So sánh React và Next.js

**1. Next.js là gì?**

Next.js là một framework được xây dựng trên nền React, bổ sung thêm các tính năng như routing tích hợp, server-side rendering, static site generation, API routes, tối ưu hình ảnh... giúp xây dựng ứng dụng React "full-stack" hoàn chỉnh hơn.

**2. Điểm khác biệt cốt lõi giữa React và Next.js là gì?**

React là thư viện chỉ tập trung vào việc dựng UI; Next.js là framework toàn diện xây trên React, cung cấp sẵn routing, các chiến lược rendering (SSR/SSG/ISR), API routes, tối ưu SEO/hình ảnh mà không cần cấu hình thêm nhiều thư viện ngoài.

**3. Routing trong React và Next.js khác nhau như thế nào?**

React thuần không có routing sẵn, phải cài và cấu hình thư viện ngoài (React Router). Next.js dùng file-based routing: cấu trúc thư mục/file trong `pages/` hoặc `app/` tự động ánh xạ thành route, không cần cấu hình thủ công.

**4. Rendering trong React và Next.js khác nhau ra sao?**

React thuần mặc định chỉ render phía client (CSR). Next.js hỗ trợ đa dạng chiến lược render: SSR, SSG, ISR và cả CSR, cho phép chọn cách render phù hợp cho từng trang.

**5. Vì sao Next.js hỗ trợ SEO tốt hơn React thuần?**

Vì Next.js có thể render HTML đầy đủ nội dung ngay trên server (SSR/SSG) trước khi gửi về trình duyệt, giúp công cụ tìm kiếm đọc được nội dung ngay lập tức; trong khi React thuần (CSR) trả về HTML gần như rỗng, bot tìm kiếm khó đọc nội dung nếu không hỗ trợ chạy JS.

**6. Hiệu năng tải trang đầu tiên (First Load) của React và Next.js khác nhau như thế nào?**

Với React thuần (CSR), trình duyệt phải tải và chạy toàn bộ JS bundle trước khi hiển thị nội dung nên First Load thường chậm hơn, dễ thấy màn hình trắng ban đầu. Với Next.js (SSR/SSG), HTML đã có sẵn nội dung khi trả về, nên nội dung hiển thị sớm hơn.

**7. Cấu trúc dự án React và Next.js khác nhau ra sao?**

React (CRA/Vite) thường có cấu trúc tự do (tự đặt `src/components`, `src/pages`...), cần tự cấu hình routing/build. Next.js có cấu trúc quy ước sẵn (thư mục `pages/` hoặc `app/`, `public/`, file `next.config.js`), phần lớn routing/build được tự động hóa theo convention.

**8. Next.js có thay thế React không? Vì sao?**

Không hẳn là "thay thế" — Next.js được xây trên nền React, vẫn dùng component, JSX, hooks của React. Next.js là lớp framework bổ sung tính năng (routing, rendering, tối ưu) cho React, chứ không phải công nghệ độc lập thay thế React.

**9. Khi nào nên dùng React thuần và khi nào nên dùng Next.js?**

Dùng React thuần khi xây dựng ứng dụng nội bộ, dashboard, SPA không cần SEO, muốn tự do cấu hình toàn bộ kiến trúc. Dùng Next.js khi cần SEO tốt (website công khai, landing page, blog, e-commerce), cần SSR/SSG, hoặc muốn có sẵn routing/API routes/tối ưu hiệu năng mà không phải tự cấu hình nhiều.

### Phần 3. Next.js

**1. App Router và Pages Router trong Next.js là gì?**

Pages Router là cách routing truyền thống của Next.js dựa trên thư mục `pages/`, mỗi file là một route, dùng `getStaticProps`/`getServerSideProps` để lấy dữ liệu. App Router là cách routing mới (từ Next.js 13+) dựa trên thư mục `app/`, hỗ trợ React Server Components, layout lồng nhau, streaming, và fetch dữ liệu trực tiếp trong component (async component).

**2. Server Component và Client Component khác nhau như thế nào?**

Server Component được render trên server, không gửi JS xuống client, phù hợp cho phần tĩnh/lấy dữ liệu, giúp giảm bundle size. Client Component được thực thi ở trình duyệt (đánh dấu bằng `"use client"`), dùng khi cần tương tác, state, hooks như `useState`/`useEffect`, xử lý sự kiện DOM.

**3. SSR (Server-Side Rendering) là gì?**

SSR là kỹ thuật render trang HTML hoàn chỉnh trên server ở mỗi request, sau đó gửi HTML đó về trình duyệt. Giúp nội dung có sẵn ngay khi tải trang, tốt cho SEO, nhưng tốn tài nguyên server hơn vì phải render lại mỗi lần có request.

**4. SSG (Static Site Generation) là gì?**

SSG là kỹ thuật tạo sẵn các trang HTML tĩnh tại thời điểm build (build time), không cần render lại mỗi request. Trang được phục vụ trực tiếp như file tĩnh, tải rất nhanh, phù hợp với nội dung ít thay đổi (blog, tài liệu, landing page).

**5. ISR (Incremental Static Regeneration) là gì?**

ISR là cơ chế cho phép cập nhật lại các trang tĩnh (đã tạo bằng SSG) sau một khoảng thời gian nhất định (revalidate) mà không cần build lại toàn bộ ứng dụng, kết hợp ưu điểm tốc độ của SSG với khả năng cập nhật dữ liệu mới như SSR.

**6. File-based Routing trong Next.js hoạt động như thế nào?**

Next.js tự động tạo route dựa trên cấu trúc thư mục/file trong `pages/` hoặc `app/`. Ví dụ file `pages/about.js` tương ứng route `/about`, hoặc trong App Router, file `app/about/page.tsx` tương ứng route `/about` — không cần khai báo route thủ công.

**7. Dynamic Route trong Next.js là gì?**

Là route có phần path động dựa trên tham số, được đặt tên file/thư mục trong dấu ngoặc vuông, ví dụ `pages/post/[id].js` hoặc `app/post/[id]/page.tsx` sẽ khớp với các URL như `/post/1`, `/post/2`..., giá trị `id` được lấy qua `params`.

**8. layout.tsx trong App Router dùng để làm gì?**

`layout.tsx` định nghĩa giao diện khung dùng chung (layout) bao quanh các trang con trong cùng route segment, ví dụ header, sidebar, footer. Layout không bị re-render khi chuyển trang giữa các route con bên trong nó, giúp giữ trạng thái và tối ưu hiệu năng.

**9. API Routes (Route Handlers) trong Next.js là gì?**

Là tính năng cho phép viết các API endpoint (backend) ngay trong dự án Next.js, không cần server riêng biệt. Ở Pages Router đặt trong `pages/api/`, ở App Router dùng file `route.ts` trong thư mục `app/` (Route Handlers), xử lý các phương thức HTTP như GET, POST...

**10. getStaticProps và getServerSideProps là gì? Chúng dùng trong trường hợp nào?**

Cả hai là hàm dùng trong Pages Router để lấy dữ liệu cho trang trước khi render:

- **getStaticProps**: chạy tại thời điểm build, dùng cho SSG — phù hợp khi dữ liệu không đổi thường xuyên.
- **getServerSideProps**: chạy ở mỗi request trên server, dùng cho SSR — phù hợp khi cần dữ liệu mới nhất theo từng lượt truy cập.

**11. next/image giúp tối ưu hình ảnh như thế nào?**

Component `next/image` tự động tối ưu hình ảnh: resize theo kích thước hiển thị, chuyển đổi định dạng hiện đại (WebP/AVIF), lazy load (chỉ tải khi cuộn tới), và cache ảnh đã tối ưu — giúp giảm dung lượng tải và cải thiện hiệu năng so với thẻ `<img>` thông thường.

**12. Middleware trong Next.js là gì?**

Middleware là đoạn code chạy trước khi request đến route đích, cho phép can thiệp vào request/response ở tầng edge (ví dụ: kiểm tra authentication, redirect, rewrite URL, xử lý header) trước khi trang thực sự được render.

**13. Làm thế nào để điều hướng giữa các trang trong Next.js?**

Dùng component `<Link>` (từ `next/link`) để điều hướng khai báo trong JSX (client-side navigation, không reload trang), hoặc dùng hook `useRouter()`/`router.push()` (Pages Router) hay `useRouter` từ `next/navigation` (App Router) để điều hướng bằng code (programmatic navigation).

**14. Metadata và SEO trong Next.js được xử lý như thế nào?**

Ở Pages Router thường dùng component `<Head>` để khai báo title, meta tag thủ công. Ở App Router, Next.js hỗ trợ export object `metadata` hoặc hàm `generateMetadata()` trong file page/layout để khai báo title, description, Open Graph... một cách khai báo (declarative), tự động render vào thẻ `<head>`.

**15. Next.js có hỗ trợ TypeScript không?**

Có. Next.js hỗ trợ TypeScript ngay từ đầu (built-in support) — chỉ cần thêm file `tsconfig.json` hoặc đổi đuôi file sang `.ts`/`.tsx`, Next.js sẽ tự nhận diện và cấu hình cần thiết.

**16. Có thể deploy dự án Next.js lên những nền tảng nào?**

Có thể deploy lên Vercel (nền tảng chính thức, tối ưu nhất cho Next.js), hoặc các nền tảng khác như Netlify, AWS (Amplify/EC2/Lambda), Docker container tự host, Railway, Render... miễn hỗ trợ Node.js runtime (với các trang cần SSR) hoặc hosting tĩnh (nếu dùng SSG/export tĩnh).

## Khó khăn gặp phải

- (Điền khó khăn gặp phải, nếu có)

## Kế hoạch ngày tiếp theo

- (Điền kế hoạch cho ngày tiếp theo)
