# Cụm 933 — Phân Tích Thi Đua

Ứng dụng web tĩnh dùng để nhập liệu, phân tích và xuất báo cáo thi đua. Có thể triển khai miễn phí bằng GitHub Pages.

## Chạy thử trên máy

Cách đơn giản nhất là mở trực tiếp file `index.html` bằng trình duyệt.

Để chạy bằng máy chủ cục bộ:

```bash
python -m http.server 8080
```

Sau đó truy cập `http://localhost:8080`.

## Đưa lên GitHub Pages

1. Tạo repository mới trên GitHub.
2. Tải toàn bộ nội dung thư mục này lên nhánh `main`.
3. Vào **Settings → Pages**.
4. Tại **Build and deployment**, chọn **Source: GitHub Actions**.
5. Workflow đi kèm sẽ tự triển khai trang web.
6. Sau khi hoàn tất, địa chỉ thường có dạng:
   `https://TEN-TAI-KHOAN.github.io/TEN-REPOSITORY/`

## Cấu trúc thư mục

```text
.
├── index.html                 # Ứng dụng chính
├── 404.html                   # Chuyển hướng khi mở đường dẫn sai
├── manifest.webmanifest       # Thông tin cài ứng dụng web
├── robots.txt                 # Thiết lập cho công cụ tìm kiếm
├── assets/favicon.svg         # Biểu tượng website
├── .nojekyll                  # Không dùng xử lý Jekyll
└── .github/workflows/
    └── deploy-pages.yml       # Tự động triển khai GitHub Pages
```

## Lưu ý rất quan trọng về dữ liệu

Ứng dụng hiện lưu dữ liệu bằng `localStorage` của trình duyệt:

- Mỗi người dùng và mỗi thiết bị có dữ liệu riêng.
- Đóng/mở lại trang trên cùng trình duyệt vẫn còn dữ liệu.
- Xóa dữ liệu trình duyệt hoặc dùng máy khác sẽ không thấy dữ liệu cũ.
- Dữ liệu nhập **không tự đồng bộ chung** giữa nhiều người.

Muốn nhiều người cùng xem và sửa một bộ dữ liệu chung, cần bổ sung cơ sở dữ liệu hoặc dịch vụ như Firebase, Supabase hay Google Sheets API. GitHub Pages chỉ lưu và phân phối mã nguồn tĩnh.

## Công nghệ

- HTML, CSS và JavaScript thuần
- Google Fonts
- html2canvas
- GitHub Pages
