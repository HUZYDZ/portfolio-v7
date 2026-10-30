# RELEASE NOTES – PORTFOLIO PHIÊN BẢN v7.0

- **Mã phiên bản:** `v7.0.0` (Bản bàn giao đánh giá A2.2)
- **Ngày cập nhật:** 30/10/2026
- **Tác giả:** Trần Đoàn Quang Huy (MSSV: 1771020359 – Lớp: CNTT17-12)
- **Repository:** https://github.com/HUZYDZ/portfolio-v7
- **URL xuất bản:** https://huzydz.github.io/portfolio-v7/ (Nhánh `main`, thư mục `/ (root)`)

---

## 1. Các thay đổi chính trong phiên bản v7
1. **Tái thiết kế hệ thống giao diện (UI Refactoring – TC5a):**
   - Áp dụng bảng màu **Đen (60% - `#0B0B0E`) – Vàng (30% - `#FFD700`) – Đỏ (10% - `#E63946`)** thông qua hệ thống biến `:root` trong `css/style.css`.
   - Bổ sung trạng thái `:focus-visible` nổi bật với viền vàng và hiệu ứng phát sáng đỏ hỗ trợ điều hướng bằng bàn phím.
   - Nâng cấp bố cục Responsive bằng CSS Grid và Flexbox cho thiết bị di động (`<= 768px`).
2. **Hoàn thiện nội dung và liên kết đa trang (`index.html` & `ket-qua.html` – TC3, TC4b):**
   - Cập nhật danh mục 3 dự án phần mềm tiêu biểu gắn liền với tài nguyên minh họa trong `assets/`.
   - Xây dựng bảng kiểm chứng HTTP Status (`200 OK`) và bảng đối chiếu Trước/Sau cải tiến giao diện ngay trên trang `ket-qua.html`.
3. **Chuẩn hóa hồ sơ kỹ thuật (TC2, TC4a):**
   - Bổ sung đầy đủ `README.md`, `AI_LOG.md` và `RELEASE_NOTES.md`.

## 2. Lỗi đã khắc phục (Bug Fixes)
- **Chuẩn hóa đường dẫn tương đối (Relative Paths):** Sử dụng thống nhất cú pháp `./css/style.css` và `./assets/...` để khi triển khai trên đường dẫn con `/portfolio-v7/` của GitHub Pages không bị lỗi `404 Not Found`.
- **Đồng bộ tên tệp nhật ký AI:** Đổi tên thống nhất từ `AI_log.md` sang `AI_LOG.md` để tránh lỗi phân biệt chữ hoa/thường trên môi trường Linux của GitHub Pages.
- **Cơ chế dự phòng ảnh đại diện:** Thêm fallback sang `./assets/avatar.svg` đảm bảo giao diện luôn hiển thị trọn vẹn ảnh.

## 3. Liên kết tiến trình Commit trên Repository
Xem toàn bộ lịch sử commit tại: https://github.com/HUZYDZ/portfolio-v7/commits/main
- **Commit 1:** Lưu trữ bản mã nguồn Portfolio gốc từ VS Code trước khi cải tiến v7.
- **Commit 2:** Thiết kế lại `css/style.css` theo tỷ lệ màu Đen-Vàng-Đỏ (60-30-10), bổ sung focus state và responsive.
- **Commit 3:** Cập nhật cấu trúc `index.html` và `ket-qua.html` đồng bộ giao diện v7.
- **Commit 4:** Hoàn thiện bộ tài liệu bàn giao `README.md`, `AI_LOG.md`, `RELEASE_NOTES.md`.

## 4. Hạn chế còn lại & Hướng phát triển tiếp theo
- **Hạn chế hiện tại:** Trang web hiện tại là trang tĩnh (Static HTML/CSS), chưa tích hợp công tắc chuyển đổi sang chế độ nền sáng (Light Mode) và biểu mẫu liên hệ trực tiếp qua API.
- **Hướng tiếp theo (v8):** Bổ sung JavaScript xử lý lọc dự án theo từ khóa công nghệ và tích hợp form gửi liên hệ tự động.