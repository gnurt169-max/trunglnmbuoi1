# E-commerce UI Improvement

## 1. Giới thiệu
Dự án là bài tập thực hành xây dựng và cải tiến giao diện thành phần quan trọng trong thương mại điện tử: **Thẻ sản phẩm (Product Card)** kết hợp với lưới danh sách sản phẩm gợi ý hôm nay. Dự án được triển khai bằng **HTML5 và CSS3 thuần túy** (không sử dụng bất kỳ thư viện hoặc framework CSS/JS bên ngoài nào), tập trung vào trải nghiệm thị giác hiện đại, cấu trúc code ngữ nghĩa, tính thẩm mỹ và khả năng tương thích Responsive trên đa thiết bị.

## 2. Website tham khảo
- **Tên website:** Tiki
- **Địa chỉ URL:** [https://tiki.vn](https://tiki.vn)
- **Khu vực đã khảo sát thực tế:**
  1. *Trang chủ (Homepage):* Bố cục tổng thể các widget "Gợi ý hôm nay", banner và luồng điều hướng.
  2. *Danh mục sản phẩm (Category Listing):* Cách thức tổ chức lưới sản phẩm và lọc dữ liệu.
  3. *Chi tiết sản phẩm (Product Detail Page):* Cấu trúc thông tin, nhãn "Chính hãng", chính sách bảo hành.
  4. *Tìm kiếm (Search Results):* Cách thức hiển thị kết quả và các thông số đánh giá sao, lượt bán.
  5. *Giỏ hàng (Shopping Cart):* Quy trình thêm sản phẩm và hiển thị số lượng giỏ hàng trên Header.

## 3. Chức năng
- **Hiển thị danh sách sản phẩm nổi bật:** Lưới 8 sản phẩm công nghệ - phụ kiện chính hãng với hình ảnh trực quan sắc nét.
- **Phân cấp giá bán trực quan:** Tách biệt rõ ràng giữa giá khuyến mãi (in đậm, cỡ lớn, màu đỏ `#d9383a`), giá niêm yết gốc (gạch ngang, màu xám `#808089`) và tỷ lệ phần trăm giảm giá (nhãn đỏ nổi bật ở góc ảnh).
- **Huy hiệu & Chỉ số tin cậy:** Tích hợp nhãn "Chính hãng", điểm đánh giá sao (Rating) kèm số lượng sản phẩm đã bán thực tế.
- **Nút hành động nhanh "Thêm vào giỏ":** Nút bấm chiếm 100% chiều rộng thẻ, màu xanh chủ đạo (`#0b74e5`), có đầy đủ phản hồi tương tác (hover và active khi click).
- **Header tiện ích:** Logo thương hiệu kèm huy hiệu "Official", thanh tìm kiếm mẫu và biểu tượng giỏ hàng tích hợp badge hiển thị số lượng sản phẩm.
- **Bố cục Responsive đa thiết bị:** Hiển thị mượt mà trên Desktop, Tablet và Mobile.

## 4. Công nghệ
- **HTML5:** Cấu trúc mã nguồn ngữ nghĩa (`<header>`, `<main>`, `<article>`, `<section>`, `<footer>`, `<button>`), tối ưu hóa khả năng truy cập (Accessibility - ARIA label).
- **CSS3 thuần (Vanilla CSS):**
  - **CSS Variables (:root):** Quản lý tập trung bảng màu, kích thước bo góc, hiệu ứng bóng đổ.
  - **CSS Grid:** Bố trí layout lưới sản phẩm linh hoạt (`grid-template-columns: repeat(4, 1fr)`).
  - **CSS Flexbox:** Điều phối hướng hiển thị theo chiều dọc (`flex-direction: column`) và căn chỉnh đáy thẻ hoàn hảo bằng `margin-top: auto`.
  - **CSS aspect-ratio & transform:** Cố định khung ảnh vuông chuẩn 1:1 và hiệu ứng zoom nhẹ (`scale`) mượt mà khi hover.
  - **CSS Line-clamp:** Giới hạn tên sản phẩm tối đa 2 dòng kèm dấu chấm lửng (`...`) tránh tràn vỡ khung hình.
  - **Media Queries:** Phân chia breakpoint rõ ràng cho Desktop, Tablet và Mobile.
- **Đồ họa SVG cục bộ (Local Vector Graphics):** Đảm bảo trang web hiển thị sắc nét 100% ngay cả khi mở offline mà không bị lỗi đứt gãy hình ảnh (broken images).

## 5. Cách chạy
Dự án được viết hoàn toàn bằng HTML/CSS tĩnh nên có thể chạy ngay lập tức mà không cần cài đặt môi trường backend hay npm:

1. **Cách 1: Mở trực tiếp trên trình duyệt**
   - Tải hoặc clone thư mục dự án về máy tính.
   - Nhấp đúp chuột trực tiếp vào file `index.html` (hoặc chuột phải chọn `Open with Google Chrome` / `Microsoft Edge` / `Safari` / `Firefox`).

2. **Cách 2: Chạy qua VS Code Live Server**
   - Mở thư mục dự án bằng Visual Studio Code.
   - Cài đặt extension **Live Server** (của Ritwick Dey).
   - Nhấp chuột phải vào file `index.html` và chọn **"Open with Live Server"** (truy cập tại `http://127.0.0.1:5500`).

3. **Cách 3: Triển khai qua GitHub Pages**
   - Đẩy mã nguồn lên kho lưu trữ GitHub cá nhân.
   - Bật tính năng **Settings > Pages > Deploy from a branch (main / root)** để xem trực tuyến trên Internet.

## 6. Cải tiến đã thực hiện
So với giao diện thẻ sản phẩm truyền thống hoặc các mẫu thẻ cơ bản trên sàn TMĐT:

| Vấn đề trên thẻ sản phẩm cũ / truyền thống | Giải pháp cải tiến trong dự án |
| :--- | :--- |
| **Thiếu phân cấp thông tin giá:** Giá gốc và giá bán thường hiển thị ngang hàng hoặc màu sắc nhạt nhòa, khó kích thích quyết định mua sắm của người dùng. | **Tách biệt phân cấp thị giác:** Đưa giá khuyến mãi lên cỡ chữ 18px in đậm màu đỏ rực `#d9383a`, dời giá gốc về màu xám gạch ngang và gắn nhãn `-xx%` nổi bật ở góc trên hình ảnh. |
| **Thiếu nút thao tác nhanh (Quick Action):** Người dùng bắt buộc phải bấm vào trang chi tiết mới có thể thêm vào giỏ, tăng thêm số lượt nhấp chuột không cần thiết. | **Tích hợp nút "Thêm vào giỏ" ngay trên thẻ:** Nút bấm full-width với màu xanh chủ đạo (`#0b74e5`), có đầy đủ hiệu ứng đổi màu khi hover và nhấn giữ (active). |
| **Lỗi lệch hàng đáy thẻ do tiêu đề dài ngắn khác nhau:** Khi tên sản phẩm 1 dòng nằm cạnh sản phẩm 3-4 dòng, các nút bấm và khu vực giá bị thụt lùi lên xuống nhấp nhô gây mất thẩm mỹ. | **Kết hợp Flexbox `margin-top: auto` & `line-clamp: 2`:** Cố định tiêu đề tối đa 2 dòng kèm chiều cao tối thiểu (`min-height: 2.8em`), đồng thời khối giá và nút mua được đẩy tự động xuống đáy thẻ, giúp toàn bộ các nút trên cùng một hàng luôn thẳng tắp. |
| **Ảnh sản phẩm méo mó hoặc không đồng bộ tỷ lệ:** Nhiều ảnh tỷ lệ khác nhau (chữ nhật, vuông) làm lệch lưới sản phẩm. | **Chuẩn hóa tỷ lệ vuông 1:1 bằng `aspect-ratio: 1 / 1`:** Kết hợp thuộc tính `object-fit: cover` và hiệu ứng phóng to nhẹ `transform: scale(1.06)` khi hover. |

## 7. Hỗ trợ từ AI
- **Vai trò của AI:** Trợ lý AI (Antigravity / Gemini) hỗ trợ phân tích trải nghiệm người dùng (UX) của sàn TMĐT Tiki, đề xuất các khu vực thông tin cần có trên thẻ sản phẩm và sinh bộ khung mã nguồn khởi đầu cho HTML5 ngữ nghĩa và bảng màu CSS Variables.
- **Vai trò và sự kiểm soát của sinh viên:**
  - Trực tiếp kiểm thử giao diện trên công cụ **Chrome DevTools** ở nhiều độ phân giải màn hình khác nhau (Desktop 1440px, Tablet iPad 768px, Mobile iPhone/Android 375px - 414px).
  - Phát hiện và tinh chỉnh lỗi thụt lùi nút bấm khi tên sản phẩm dài ngắn khác nhau bằng cách bổ sung kỹ thuật Flexbox `margin-top: auto` kết hợp `line-clamp: 2` và `min-height`.
  - Tự thiết kế hệ thống vector ảnh SVG cục bộ độc lập để loại bỏ sự phụ thuộc vào đường link ảnh online, đảm bảo bài tập nộp luôn chấm điểm mượt mà ở cả chế độ offline.
  - Bổ sung hệ thống comment giải thích chi tiết trong cả mã HTML và CSS để sẵn sàng tự tin thuyết minh trước giảng viên.
# trunglnmbuoi1
