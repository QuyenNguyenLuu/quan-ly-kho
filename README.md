# Coco Cottage — Quản lý kho hàng

Phần mềm theo dõi nhập – xuất – tồn kho, chạy hoàn toàn trên trình duyệt (không cần server).


## Chức năng
- Quản lý người dùng (thêm / sửa / xoá, phân vai trò Quản trị viên / Nhân viên)
- Danh mục hàng hoá (mã hàng, tên hàng, số lượng)
- Phòng ban (Kho chính, Nhà hàng, Phòng ngủ…)
- Nhập hàng vào kho, xuất hàng ra các phòng ban
- Báo cáo nhập – xuất – tồn theo tháng hoặc khoảng thời gian tuỳ chọn, xuất CSV

Tài khoản mặc định: **admin** / mật khẩu **admin**

## Giao diện
Theme lấy cảm hứng từ website Coco Cottage (coco-cottage.com.vn): nền xanh rêu, chữ trắng, tiêu đề serif (Playfair Display), nút bo tròn. Có footer thông tin liên hệ như trên website.

## Logo
Logo Coco Cottage đã được nhúng sẵn (base64) trong `index.html`, không cần file ảnh rời — vẫn hoạt động khi đưa lên GitHub Pages.

## Tuỳ chỉnh tên công ty
Mở `index.html`, tìm dòng gần đầu thẻ `<script>`:
```js
const CLIENT = { name:'Coco Cottage', short:'Mũi Né – Phan Thiết' };
const INFO = { address:[...], phone:'...', email:'...', tagline:'...' }; // sửa nội dung footer tại đây

```
Đổi `CLIENT.name` thành tên công ty khách hàng thực tế.

## Đưa lên GitHub Pages
1. Tạo repository mới trên GitHub (ví dụ: `quan-ly-kho`).
2. Upload `index.html` và `README.md` (Add file → Upload files → Commit).
3. Settings → Pages → Source: nhánh `main`, thư mục `/ (root)` → Save.
4. Đợi 1–2 phút, truy cập: `https://<tên-github>.github.io/quan-ly-kho/`

## Lưu ý về dữ liệu
- Dữ liệu lưu bằng **localStorage của trình duyệt** — chỉ nằm trên máy/trình duyệt đang dùng, không đồng bộ giữa các thiết bị.
- Nếu cần nhiều người dùng chung một kho dữ liệu, cần kết nối backend (Google Sheets, Firebase…). Có thể bổ sung sau.

## Mật khẩu & bảo mật
- Mỗi tài khoản có mật khẩu riêng; mật khẩu được **băm SHA-256** trước khi lưu (không lưu dạng chữ thô).
- Tài khoản mặc định: `admin` / `admin` — nên đổi ngay sau lần đăng nhập đầu (nút **Đổi mật khẩu** ở góc trên phải).
- Quản trị viên đặt/đổi mật khẩu cho tài khoản khác trong mục **Người dùng**.
- **Lưu ý:** đây là app chạy phía trình duyệt (localStorage) nên chỉ phù hợp kiểm soát truy cập nội bộ, không phải bảo mật cấp doanh nghiệp. Muốn bảo mật thật cần backend (Google Sheets/Firebase…).