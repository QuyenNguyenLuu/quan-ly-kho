# Quản lý kho hàng

Phần mềm theo dõi nhập – xuất – tồn kho, chạy hoàn toàn trên trình duyệt (không cần server).


## Chức năng
- Quản lý người dùng (thêm / sửa / xoá, phân vai trò Quản trị viên / Nhân viên)
- Danh mục hàng hoá (mã hàng, tên hàng, số lượng)
- Phòng ban (Kho chính, Nhà hàng, Phòng ngủ…)
- Nhập hàng vào kho, xuất hàng ra các phòng ban
- Báo cáo nhập – xuất – tồn theo tháng hoặc khoảng thời gian tuỳ chọn, xuất CSV

Tài khoản mặc định: **admin**

## Tuỳ chỉnh tên công ty
Mở `index.html`, tìm dòng gần đầu thẻ `<script>`:
```js
const CLIENT = { name:'Kho Vận Minh Phát', short:'Quản lý kho' }; // công ty sử dụng phần mềm

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
