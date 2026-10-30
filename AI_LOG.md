# AI LOG – BUỔI 7, TIẾT 3

> Điền vào `[ ... ]`, tích `[x]` vào lựa chọn phù hợp. Ghi đúng việc đã làm; chưa kiểm tra thì ghi “Chưa kiểm tra”. Không cần chép toàn bộ cuộc trò chuyện AI.

## Thông tin sinh viên

- Họ và tên: Trần Đoàn Quang Huy
- Mã sinh viên – Lớp: 1771020359 – CNTT17-12
- Ngày thực hiện: 30/10/2026
- Link repository: https://github.com/HUZYDZ/portfolio-v7
- URL website: https://huzydz.github.io/portfolio-v7/
- Tình huống: [x] Website của tôi  [ ] Repo luyện của giảng viên

## 1. Nhận định của tôi trước khi hỏi AI

- Trang/thao tác gặp lỗi: Giao diện ở `index.html`, `ket-qua.html` và tệp `css/style.css`; thao tác đẩy mã nguồn từ VS Code lên GitHub chính cá nhân (`HUZYDZ`) theo từng giai đoạn commit.
- Mong muốn và hiện tượng thực tế:
  - **Mong muốn:** Đẩy bản gốc từ VS Code lên GitHub trước để lưu mốc lịch sử ban đầu (minh chứng Before), sau đó mới cải tiến giao diện web theo tỷ lệ màu Vàng – Đỏ – Đen, đồng bộ đường dẫn ảnh và chia từng commit rõ ràng theo đúng tiến trình sửa đổi.
  - **Hiện tượng thực tế:** Bản code mới nằm ở VS Code local (trong thư mục đã có sẵn `.git` cũ nhưng chưa trỏ về repo `HUZYDZ/portfolio-v7`), quên cú pháp đẩy bản gốc lên trước; giao diện cũ chưa phân bổ tỷ lệ màu Vàng – Đỏ – Đen hợp lý, trạng thái focus bàn phím mờ và cần đảm bảo không bị lỗi 404 khi tải ảnh trong `assets/` trên GitHub Pages.
- Dữ kiện đã kiểm tra (cấu trúc tệp, Request URL, Status…):
  - Cấu trúc thư mục hiện tại gồm: `index.html`, `ket-qua.html`, `css/style.css`, `README.md` và thư mục `assets/` chứa `791975572_1060704449904978_7434436045093909714_n.jpg`, `avatar.svg`, `du-an-1.svg`, `du-an-2.svg`, `du-an-3.svg`.
  - Kiểm tra trên trình duyệt local (F12 -> Network): các tệp tải ở local bình thường nhưng nếu đưa lên đường dẫn con `/portfolio-v7/` của GitHub Pages cần dùng đường dẫn tương đối (`./`) và cần cơ chế dự phòng (`onerror`) cho ảnh đại diện.
- Tôi nghi nguyên nhân là:
  - Chưa cấu hình lại `remote origin` trỏ về tài khoản GitHub `HUZYDZ` và chưa chia tách quy trình `git add` / `git commit` theo từng nhóm tệp (bản gốc -> CSS -> HTML -> Docs).
  - Tệp `css/style.css` chưa sử dụng hệ thống biến `:root` theo tỷ lệ thiết kế tiêu chuẩn nên khi phối 3 màu mạnh (Vàng – Đỏ – Đen) dễ bị rối mắt hoặc thiếu độ tương phản.
- Vì sao tôi nhận định như vậy: Vì bài đánh giá A2.2 yêu cầu kiểm tra lịch sử tiến trình Git (TC1), đối chiếu phiên bản Local – Repo – URL (TC4b) và giải thích cải tiến giao diện trước/sau có căn cứ (TC5a).

## 2. Tôi hỏi AI và nhận được gợi ý

- Nguồn: [x] Công cụ AI: Gemini  [ ] Phản hồi mẫu của giảng viên
- Câu hỏi/prompt tôi đã gửi (hoặc tình huống của phản hồi mẫu):

  "đây là bài kiểm tra của tôi và tôi cần đẩy lên github và có từng thay đổi repo theo từng thay đổi hãy chỉ từng bước và hiện tại , và hãy cải tiến web theo các tỉ lệ mầu vàng đỏ đen hãy thiết kế code lại v.v hãy làm đầy đủ"
  "từ từ hãy bắt đầu lại từ đầu nhưng yêu với yêu cầu trên tôi đã đưa nhưng hiện tại bài này tôi mới viết ở vs code chưa đẩy lên github chính của tôi nên cần đẩy lên trước rồi mới thay đổi repo vì nó là minh chứng để lấy điểm tất nhiên tôi cũng đã quên cách đẩy lên hãy làm từ bước đẩy lên git rồi mới bắt đầu sửa code"

- Gợi ý chính của AI:

  1. **Về quy trình Git & Repository:** Khởi tạo và cấu hình `git remote add origin https://github.com/HUZYDZ/portfolio-v7.git`, thực hiện **Commit 1** đẩy nguyên trạng bản gốc từ VS Code lên nhánh `main` trước để lưu mốc đối chiếu. Sau đó mới sửa code và tách thành **Commit 2** (nâng cấp `css/style.css`), **Commit 3** (cập nhật `index.html`, `ket-qua.html`) và **Commit 4** (hoàn thiện bộ hồ sơ `README.md`, `AI_LOG.md`, `RELEASE_NOTES.md`).
  2. **Về cải tiến giao diện Vàng – Đỏ – Đen:** Áp dụng nguyên tắc phối màu **60-30-10** trong `:root` của `css/style.css`:
     - **60% Đen (`#0B0B0E`, `#15151B`):** Màu nền chủ đạo giúp tôn chữ trắng/vàng, đạt độ tương phản chuẩn WCAG AAA (> 14:1).
     - **30% Vàng (`#FFD700`):** Màu thứ cấp cho hệ thống tiêu đề H1–H3, đường viền thẻ dự án và khung `:focus-visible` khi điều hướng bằng phím `Tab`.
     - **10% Đỏ (`#E63946`):** Màu nhấn (Accent) cho các nút hành động chính (`.btn-primary`), huy hiệu `v7.0` và hiệu ứng đổ bóng khi hover.
  3. **Về chuẩn hóa tài nguyên trên GitHub Pages:** Dùng đường dẫn tương đối `./css/style.css`, `./assets/du-an-1..3.svg` và thêm thuộc tính `onerror="this.onerror=null; this.src='./assets/avatar.svg';"` cho ảnh đại diện để tránh lỗi gãy ảnh.

## 3. Quyết định của tôi

- [ ] Chấp nhận gợi ý
- [x] Chỉnh sửa gợi ý rồi áp dụng
- [ ] Bác bỏ gợi ý

- Tôi quyết định làm gì:
  - Áp dụng lộ trình 4 bước commit riêng biệt (đẩy bản gốc lên GitHub `HUZYDZ/portfolio-v7` trước rồi mới tuần tự commit bản sửa CSS, HTML và tài liệu).
  - Áp dụng bảng màu 60-30-10 (Đen – Vàng – Đỏ) vào `css/style.css`, đồng thời chỉnh sửa nội dung `index.html` và `ket-qua.html` để bổ sung thông tin cá nhân thực tế, dự án tiêu biểu và bảng đối chiếu kết quả kiểm chứng HTTP Status 200.
  - Chuẩn hóa tên tệp nhật ký thành `AI_LOG.md` theo đúng quy định mục 3.2 của hướng dẫn A2.2.
- Lý do, dựa trên dữ kiện nào:
  - Việc đẩy bản gốc lên ở Commit 1 giúp giảng viên dễ dàng xem `git diff` giữa bản cũ và bản v7 trên GitHub.
  - Tỷ lệ 60% Đen – 30% Vàng – 10% Đỏ giải quyết triệt để bài toán thẩm mỹ và khả năng đọc, không gây chói mắt như khi dùng màu đỏ hoặc vàng làm nền lớn.

## 4. Thực hiện và kiểm chứng

- Tệp/vị trí đã sửa (không sửa thì ghi rõ):
  - `css/style.css`: Viết lại hệ thống biến `:root` (Đen - Vàng - Đỏ), bổ sung `:focus-visible`, hiệu ứng card dự án và `@media (max-width: 768px)`.
  - `index.html` và `ket-qua.html`: Cập nhật bố cục HTML5 ngữ nghĩa, liên kết đúng các tệp trong `assets/` và thêm bảng đối chiếu Trước/Sau cải tiến giao diện.
  - `README.md`, `AI_LOG.md`, `RELEASE_NOTES.md`: Cập nhật đầy đủ hồ sơ bàn giao bản v7.
- Nội dung thay đổi hoặc cách xử lý khác: Đổi tên tệp mẫu `AI_log.md` thành `AI_LOG.md` để khớp chính xác chữ hoa/thường trên môi trường Linux của GitHub Pages.
- Commit của bản sửa, nếu có:
  - Commit 1: `chore: Luu ban ma nguon Portfolio goc truoc khi cai tien UI v7`
  - Commit 2: `style(css): Thiet ke lai he thong mau Den-Vang-Do (60-30-10), bo sung focus state va responsive`
  - Commit 3: `feat(html): Cap nhat cau truc index.html va ket-qua.html dong bo giao dien v7`
  - Commit 4: `docs(v7): Bo sung ho so README.md, AI_LOG.md va RELEASE_NOTES.md theo rubric A2.2`
- Bản sửa đã deploy: [x] Có  [ ] Chưa  [ ] Không phát sinh bản sửa

| Nội dung kiểm tra | Trước xử lý | Sau xử lý/thử lại |
| --- | --- | --- |
| Request URL và Status của tài nguyên liên quan | Chỉ mới chạy ở local VS Code; chưa có URL GitHub Pages công khai trên tài khoản `HUZYDZ`. | Đã deploy tại `https://huzydz.github.io/portfolio-v7/`; kiểm tra F12 -> Network: `index.html`, `ket-qua.html`, `css/style.css`, `du-an-1.svg`, `du-an-2.svg`, `du-an-3.svg` đều báo `Status: 200 OK`. |
| Giao diện/chức năng trên URL website | Màu sắc chưa phân cấp rõ, viền focus mặc định khó nhìn, chưa có bảng đối chiếu kiểm chứng trực tiếp trên trang Kết quả. | Giao diện Đen – Vàng – Đỏ (60-30-10) hiển thị sắc nét, độ tương phản cao, bấm phím `Tab` hiện viền vàng-đỏ rõ ràng, chuyển trang mượt giữa `index.html` và `ket-qua.html`, responsive tốt trên mobile. |

- Cách thử lại và kết quả thực tế:
  - Sau khi `git push` lên nhánh `main`, chờ GitHub Actions deploy xong, mở `https://huzydz.github.io/portfolio-v7/` bằng cửa sổ ẩn danh (Incognito).
  - Kiểm tra tab Network (`Ctrl + R`), bấm thử toàn bộ liên kết điều hướng, thu nhỏ màn hình xuống 375px và nhấn phím `Tab` kiểm tra trạng thái focus. Tất cả hoạt động đúng thiết kế.
- Căn cứ để đối chiếu (URL tệp, commit, đường dẫn ảnh chụp hoặc dữ kiện quan sát):
  - Lịch sử 4 commit trên repo: `https://github.com/HUZYDZ/portfolio-v7/commits/main`
  - Trang kết quả và bảng đối chiếu trực tiếp: `https://huzydz.github.io/portfolio-v7/ket-qua.html`

## 5. Kết luận

- [x] Đã xử lý được  [ ] Xử lý được một phần  [ ] Chưa xử lý được
- Điều tôi rút ra hoặc việc cần làm tiếp:
  - Rút ra kinh nghiệm quản lý phiên bản Git: luôn commit bản gốc trước khi refactor diện rộng để giữ lịch sử `diff` rõ ràng, và chú ý tính phân biệt chữ hoa/thường (case-sensitive) của tên tệp khi deploy lên GitHub Pages.
  - Việc cần làm tiếp ở phiên bản sau: tích hợp thêm bộ lọc dự án bằng JavaScript và công tắc chuyển đổi chế độ Sáng/Tối (Light/Dark mode).

---

*Tệp là minh chứng MC2 để nhận định mức đạt của tiết học; không tính điểm MC2 riêng. Nếu có tình huống khác, sao chép mục 1–5 để ghi thêm.*