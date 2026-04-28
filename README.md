# ScanToPDF (Offline)

Ứng dụng web chạy hoàn toàn trên trình duyệt để:
- Nhập nhiều ảnh từ máy hoặc chụp bằng camera.
- Tự bắt góc giấy tờ, chỉnh lại thủ công nếu cần.
- Làm phẳng phối cảnh, tăng sáng/tương phản, áp bộ lọc tài liệu.
- Xuất ra PDF hoặc ảnh JPG/PNG.

## Cách chạy
Vì app chỉ gồm file tĩnh, bạn có thể mở trực tiếp `index.html` bằng trình duyệt hiện đại.

Khuyến nghị dùng server local để camera hoạt động ổn định hơn:

```bash
python3 -m http.server 8080
```

Sau đó mở: `http://localhost:8080`

## Tính năng chính

- **Upload nhiều ảnh**: chọn cùng lúc nhiều ảnh để tạo bộ scan.
- **Camera capture**: mở camera, chụp từng trang.
- **Auto detect góc**:
  - App tự ước lượng vùng tài liệu khi thêm ảnh/chụp ảnh/xoay ảnh.
  - Nút **"Tự bắt góc"** để chạy lại thuật toán cho trang hiện tại.
- **Kéo 4 góc thủ công**: luôn có thể chỉnh tay nếu nhận diện chưa chuẩn.
- **Làm phẳng phối cảnh**: đưa trang nghiêng về dạng vuông vức.
- **Filter**: grayscale, đen-trắng tài liệu, sepia, invert.
- **Xuất file**:
  - PDF nhiều trang (A4/A5/Letter/Legal, dọc hoặc ngang)
  - JPG/PNG cho trang đang chọn

## Lưu ý

- Ảnh lớn được tự giảm kích thước xử lý (max cạnh dài ~2200px) để thao tác mượt hơn.
- Tất cả xử lý diễn ra cục bộ trên trình duyệt; không cần upload ảnh lên server.
- Auto-detect là heuristic: trong một số ảnh phức tạp, bạn nên kéo tay 4 góc để có kết quả tốt nhất.

## Cấu trúc dự án

- `index.html`: toàn bộ giao diện + logic xử lý ảnh + xuất PDF.
- `README.md`: hướng dẫn sử dụng.
