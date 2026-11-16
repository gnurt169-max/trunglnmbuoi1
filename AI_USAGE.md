# AI Usage Log

## 1. Công cụ AI
- **Tên công cụ:** Trợ lý trí tuệ nhân tạo **Antigravity / Gemini** (Google DeepMind).
- **Môi trường sử dụng:** Tích hợp trực tiếp trong môi trường phát triển mã nguồn IDE.

## 2. Mục đích sử dụng
- Khảo sát và phân tích giao diện người dùng (UI/UX) của sàn thương mại điện tử Tiki.vn tại 5 khu vực trọng điểm.
- Đề xuất ý tưởng cải tiến cấu trúc Thẻ sản phẩm (Product Card) nhằm nâng cao tỷ lệ chuyển đổi và trải nghiệm thị giác.
- Hỗ trợ xây dựng bộ khung mã nguồn khởi tạo bằng HTML5 và CSS3 thuần (không sử dụng framework hoặc thư viện ngoài).
- Tư vấn các kỹ thuật CSS hiện đại giải quyết bài toán Responsive (CSS Grid) và căn chỉnh các phần tử đáy thẻ (Flexbox).

## 3. Prompt đã sử dụng
Dưới đây là tóm tắt các câu lệnh prompt chính đã gửi cho AI trong quá trình thực hiện bài tập:

1. **Prompt phân tích website tham khảo:**
   > *"Hãy phân tích cấu trúc giao diện của website thương mại điện tử Tiki.vn tại 5 khu vực: Trang chủ, Danh mục sản phẩm, Trang chi tiết sản phẩm, Trang kết quả tìm kiếm và Giỏ hàng. Chỉ ra điểm mạnh và những điểm cần cải tiến ở thẻ sản phẩm (Product Card)."*

2. **Prompt đề xuất giải pháp thiết kế:**
   > *"Dựa trên các nhược điểm của thẻ sản phẩm hiện tại, hãy đề xuất bố cục thẻ sản phẩm cải tiến: cần có nhãn giảm giá ở góc trên bên trái, hình ảnh vuông 1:1 có hiệu ứng zoom nhẹ, nhãn Chính hãng, tên sản phẩm giới hạn 2 dòng, đánh giá sao kèm lượt bán, phân cấp giá rõ ràng và nút 'Thêm vào giỏ' full-width màu xanh Tiki."*

3. **Prompt tạo mã nguồn và tối ưu kỹ thuật:**
   > *"Hãy viết mã nguồn hoàn chỉnh bằng HTML5 và CSS3 thuần cho lưới 8 sản phẩm công nghệ. Yêu cầu bắt buộc: Dùng CSS Grid chia 4 cột Desktop, 2 cột Tablet và Mobile; Dùng Flexbox với `margin-top: auto` để mọi nút 'Thêm vào giỏ' luôn thẳng hàng ngang dưới đáy thẻ bất kể tên sản phẩm dài hay ngắn; Kèm comment giải thích chi tiết từng khối code."*

## 4. Kết quả AI đề xuất

### 4.1. Bảng phân tích 5 khu vực khảo sát tại Tiki.vn
AI đã tổng hợp bảng khảo sát chi tiết như sau:

| Khu vực khảo sát | Đặc điểm giao diện hiện tại | Nhận xét & Điểm cần cải tiến |
| :--- | :--- | :--- |
| **1. Trang chủ (Homepage)** | Trưng bày nhiều block gợi ý "Giá tốt hôm nay", "Top Deal". | Nhiều banner quảng cáo lấn át; thẻ sản phẩm ở một số widget chưa có nút thêm nhanh vào giỏ. |
| **2. Danh mục sản phẩm** | Lưới sản phẩm phân chia theo ngành hàng công nghệ, gia dụng,... | Khoảng cách giữa các thẻ chưa thực sự tối ưu trên màn hình cỡ trung; giá gốc mờ nhạt. |
| **3. Chi tiết sản phẩm** | Đầy đủ thông số kỹ thuật, đánh giá của người mua, chính sách đổi trả. | Thông tin phong phú nhưng phần thông điệp bảo đảm "Chính hãng" cần được làm nổi bật từ ngoài danh sách. |
| **4. Tìm kiếm sản phẩm** | Hiển thị kết quả tìm kiếm theo từ khóa kèm bộ lọc phân loại. | Tiêu đề sản phẩm dài ngắn không đồng đều làm cho chiều cao các thẻ trong cùng hàng bị so le nếu không cắt dòng. |
| **5. Giỏ hàng & Header** | Header có ô tìm kiếm rộng, icon giỏ hàng kèm số lượng sản phẩm. | Cần giữ sự tinh giản, hiện đại; biểu tượng giỏ hàng cần có badge màu đỏ nổi bật để người dùng dễ theo dõi. |

### 4.2. Cấu trúc mã nguồn do AI gợi ý
- Cấu trúc cây HTML5 ngữ nghĩa với các thẻ chuẩn: `<header>`, `<main>`, `<article class="product-card">`, `<section>`, `<footer>`.
- Khung CSS Variables (`:root`) để định nghĩa bảng mã màu chuẩn `#0b74e5` (Xanh Tiki), `#d9383a` (Đỏ khuyến mãi), `#808089` (Xám giá gốc).
- Đoạn mã mẫu sử dụng CSS Grid `repeat(4, 1fr)` và thuộc tính `aspect-ratio: 1 / 1`.

## 5. Kiểm tra và điều chỉnh của sinh viên
Quá trình rà soát và tinh chỉnh thực tế trên mã nguồn do AI sinh ra:

1. **Loại bỏ nhận xét chưa được kiểm chứng của AI:**
   - Trong phản hồi ban đầu, AI nhận xét rằng *"Tiki bản web máy tính thiếu tính năng tìm kiếm bằng hình ảnh so với Shopee"*. Sau khi trực tiếp mở `tiki.vn` trên trình duyệt máy tính để xác minh, sinh viên nhận thấy phiên bản web của hầu hết các sàn TMĐT tại Việt Nam đều ưu tiên tìm kiếm bằng từ khóa văn bản và việc đề xuất thêm nút camera tìm kiếm ảnh trên desktop là không thực sự cần thiết và dễ gây rối giao diện. Do đó, sinh viên đã chủ động loại bỏ nhận xét này khỏi báo cáo.

2. **Kiểm tra thực tế trên Chrome DevTools và sửa lỗi thụt lùi nút bấm:**
   - Khi áp dụng tên sản phẩm thực tế (có sản phẩm tên chỉ 1 dòng như *"Củ Sạc Nhanh GaN 65W Type-C"*, nhưng có sản phẩm tên dài đến 3-4 dòng như *"Chuột Không Dây Công Thái Học Wireless Slient Chống Mỏi Cổ Tay..."*), mã nguồn ban đầu của AI khiến chiều cao thẻ bị xô lệch và các nút "Thêm vào giỏ" nằm nhấp nhô không thẳng hàng ngang.
   - **Cách sinh viên điều chỉnh:**
     + Bổ sung thuộc tính `-webkit-line-clamp: 2`, `display: -webkit-box`, `-webkit-box-orient: vertical`, `overflow: hidden` và đặt `min-height: 2.8em` cho class `.product-title` để cố định không gian văn bản 2 dòng.
     + Đặt `display: flex; flex-direction: column` cho `.product-card` và `.product-info`.
     + Thêm thuộc tính cốt lõi **`margin-top: auto`** cho container `.product-footer` (chứa giá và nút mua). Thuộc tính này lập tức hấp thụ toàn bộ khoảng trống còn dư và ép các khối giá cùng nút "Thêm vào giỏ" xuống đáy thẻ, giúp 100% các nút trên cùng một hàng luôn thẳng tắp một cách hoàn hảo.

3. **Thay thế hình ảnh ngoài bằng SVG cục bộ (Local Assets):**
   - Ban đầu AI đề xuất các đường dẫn ảnh online từ Unsplash / Placeholder CDN. Để tránh tình trạng hình ảnh bị lỗi hiển thị (broken images) khi giáo viên chấm bài trong môi trường không có internet hoặc khi server bên ngoài chặn truy cập, sinh viên đã chủ động tạo 8 file ảnh vector SVG cục bộ đặt trong thư mục `images/` với màu sắc và minh họa sản phẩm sắc nét.

## 6. Phần tôi hiểu và có thể giải thích (Sẵn sàng thuyết trình)

Sinh viên hoàn toàn nắm vững và có thể trình bày trực tiếp các kiến thức kỹ thuật sau:

### 6.1. Cấu trúc thẻ HTML5 ngữ nghĩa (Semantic HTML5)
- `<header class="site-header">`: Đại diện cho phần đầu trang, chứa định danh thương hiệu, công cụ điều hướng tìm kiếm và giỏ hàng.
- `<main class="main-content">`: Chứa nội dung chính duy nhất của trang web là danh sách sản phẩm gợi ý.
- `<article class="product-card">`: Đại diện cho một đơn vị nội dung độc lập, khép kín (một thẻ sản phẩm hoàn chỉnh), giúp máy tìm kiếm (SEO) và trình đọc màn hình dễ dàng phân tích ngữ cảnh.
- `<button type="button">`: Sử dụng thẻ button với thuộc tính rõ ràng cho hành động tương tác thay vì thẻ `<div>` hay `<a>` không đúng chuẩn truy cập.

### 6.2. Cơ chế hoạt động của CSS Grid trong danh sách sản phẩm
- `display: grid;`: Thiết lập ngữ cảnh định dạng dạng lưới 2 chiều cho phần tử cha `.product-grid`.
- `grid-template-columns: repeat(4, 1fr);`: Định nghĩa lưới gồm đúng 4 cột có kích thước bằng nhau (`1fr` = 1 fraction unit), tự động chia đều chiều rộng container cho 4 thẻ sản phẩm trên mỗi hàng.
- `gap: 16px;`: Tạo khoảng cách đồng đều giữa các hàng và các cột mà không cần dùng `margin` âm hay `padding` phức tạp như cách làm cũ.

### 6.3. Kỹ thuật Flexbox căn chỉnh đáy thẻ (`margin-top: auto`)
- Cấu trúc: Thẻ cha `.product-card` có `display: flex; flex-direction: column;`.
- Phần tử `.product-footer` chứa giá và nút mua hàng được áp dụng `margin-top: auto;`.
- **Nguyên lý hoạt động:** Trong một Flex container theo trục dọc (`flex-direction: column`), khi một phần tử con được gán `margin-top: auto`, trình duyệt sẽ tính toán toàn bộ khoảng cách trống còn lại của container và tự động phân bổ vào lề trên của phần tử đó. Nhờ vậy, phần tử này sẽ bị đẩy sát xuống mép dưới cùng của thẻ, bất kể phần nội dung tiêu đề phía trên dài 1 dòng hay 2 dòng.

### 6.4. Media Queries và tính tương thích Responsive
- **Desktop (> 1024px):** Lưới hiển thị 4 cột (`repeat(4, 1fr)`), thanh tìm kiếm rộng 600px.
- **Tablet (600px - 1024px):** Chuyển sang 2 cột (`grid-template-columns: repeat(2, 1fr)`), thanh tìm kiếm tự động thu gọn còn 450px để bảo đảm sự cân đối.
- **Mobile (< 600px):**
  + Header tự động ngắt dòng (`flex-wrap: wrap`), thanh tìm kiếm được đẩy xuống vị trí thứ 3 (`order: 3`) chiếm trọn 100% chiều ngang màn hình.
  + Lưới sản phẩm sử dụng `repeat(auto-fit, minmax(150px, 1fr))` cho phép hiển thị 2 cột vừa vặn trên hầu hết các dòng smartphone từ 360px trở lên, kích thước chữ và nút bấm được thu nhỏ nhẹ để tránh tràn viền.
