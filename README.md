# 🎣 Hồ Câu Đài Lam Sơn

Ứng dụng web cài được lên điện thoại (PWA) để quản lý hồ câu: sơ đồ chỗ ngồi, tính tiền theo giờ, bán hàng và kho, cá thả/cá câu, báo cáo thu chi. Chạy offline, không cần máy chủ, dữ liệu lưu trên máy.

## Tính năng
- Sơ đồ nhiều hồ, trạng thái chỗ trống/đang câu, đồng hồ từng chỗ
- Mở phiên, gọi đồ/thuê cần gắn vào phiên, ghi cá câu (mang về / thả / bán lại), thanh toán
- Tính tiền theo ca câu do chủ hồ tự cài đặt (tên ca, số giờ, giá ca, giá mỗi giờ lố). Tiền = giá ca + giờ lố (làm tròn lên) + dịch vụ − cá bán lại
- Sơ đồ hiện thời gian còn lại của ca, ô hết ca có viền đỏ
- Kho và bán lẻ theo đơn (nhiều món, chọn hình thức thanh toán), cảnh báo sắp hết hàng
- Thả cá theo hồ, ước tính tồn cá, cảnh báo cần thả thêm
- Báo cá: chỉ chủ hồ được báo (trong phiên câu, nút 🐟 Báo cá). Mỗi ô câu trên sơ đồ hiện số con và tổng kg cá; ô vừa lên cá nhấp nháy đỏ 10 phút kèm loại cá và kg của con mới nhất, khách cùng xem được; bấm vào ô để xem từng con cá và giờ lên cá
- Tài khoản chủ hồ: chưa đăng nhập (chế độ khách) chỉ xem được Sơ đồ; đăng nhập để vào các menu quản lý, đổi mật khẩu trong Cài đặt
- Báo cáo theo từng ô câu (lượt, giờ, kg cá, doanh thu, ô doanh thu cao nhất) theo ngày/tháng
- Chốt sổ tự động lúc 24h mỗi ngày vào database IndexedDB trên máy (mở app sau đó vẫn tự chốt bù các ngày bị lỡ)
- Trên Chrome/Edge máy tính: chọn thư mục app trong Cài đặt để ghi thêm mỗi ngày 1 file `du-lieu/YYYY-MM-DD.json`
- Menu Doanh thu (chủ hồ): xem theo tháng, từng ngày (tiền câu, dịch vụ, bán lẻ, chi, lãi, theo hồ, hình thức thanh toán, danh sách hóa đơn), xuất CSV mở bằng Excel
- Báo cáo ngày/tháng, ghi chi phí (nhập cá, nhập hàng tự ghi chi)
- In phiếu tạm tính / hóa đơn thanh toán (khổ giấy nhiệt 58 hoặc 80mm), hóa đơn bán lẻ; in lại hóa đơn cũ ở tab Báo cáo và Kho & bán; tên, địa chỉ, SĐT, lời cảm ơn chỉnh trong Cài đặt
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
Đăng nhập trên máy chủ (tài khoản hiện chỉ khóa giao diện trên máy này, không thay thế bảo mật thật), nhiều tài khoản nhân viên, đặt chỗ online, giải câu, nhân sự, đồng bộ nhiều thiết bị. Dữ liệu chỉ nằm trên một điện thoại, cần có backend nếu muốn dùng nhiều máy.
