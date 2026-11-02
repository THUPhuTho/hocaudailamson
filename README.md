# 🎣 Quản lý hồ câu

Ứng dụng web cài được lên điện thoại (PWA) để quản lý hồ câu: sơ đồ chỗ ngồi, tính tiền theo giờ, bán hàng và kho, cá thả/cá câu, báo cáo thu chi. Chạy offline, không cần máy chủ, dữ liệu lưu trên máy.

## Tính năng
- Sơ đồ nhiều hồ, trạng thái chỗ trống/đang câu, đồng hồ từng chỗ
- Mở phiên, gọi đồ/thuê cần gắn vào phiên, ghi cá câu (mang về / thả / bán lại), thanh toán
- Tiền = giờ (làm tròn lên) + dịch vụ − cá bán lại
- Kho và bán lẻ, cảnh báo sắp hết hàng
- Thả cá theo hồ, ước tính tồn cá, cảnh báo cần thả thêm
- Báo cáo ngày/tháng, ghi chi phí (nhập cá, nhập hàng tự ghi chi)
- Sao lưu/khôi phục bằng file JSON

## Đưa lên GitHub và chạy trên điện thoại
1. Tạo repository mới trên GitHub, giải nén thư mục này và tải toàn bộ file lên (nhánh `main`).
2. Vào **Settings → Pages → Source: GitHub Actions**.
3. Đợi tab **Actions** chạy xong, link có dạng `https://<tên-bạn>.github.io/<tên-repo>/`.
4. Mở link trên điện thoại:
   - Android (Chrome): menu ⋮ → **Cài đặt ứng dụng / Thêm vào màn hình chính**
   - iPhone (Safari): nút Chia sẻ → **Thêm vào Màn hình chính**

Chạy thử trên máy tính: `python3 -m http.server 8000` rồi mở http://localhost:8000.

## Cấu trúc
`index.html` (toàn bộ giao diện và logic), `manifest.json`, `sw.js` (offline), `icon-*.png`, `.github/workflows/pages.yml` (tự triển khai).

## Chưa có trong bản này
Đăng nhập/phân quyền, đặt chỗ online, giải câu, nhân sự, đồng bộ nhiều thiết bị. Dữ liệu chỉ nằm trên một điện thoại, cần có backend nếu muốn dùng nhiều máy.
