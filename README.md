# Habit Tracker - Backend API

> **Người thực hiện:** Võ Lan Anh (Backend Engineer)
> **Stack:** Node.js, Express, Supabase (PostgreSQL)

## 1. Dành cho Phạm Duy (Frontend Engineer)

Dưới đây là danh sách các API Backend đã hoàn thiện để Frontend gọi (Base URL hiện tại đang chạy ở `http://localhost:3000`):

| Method | Endpoint | Mô tả | Dữ liệu gửi lên (Body) |
|---|---|---|---|
| **GET** | `/api/health` | Kiểm tra trạng thái Server | Trống |
| **GET** | `/api/habits` | Lấy danh sách thói quen | Trống |
| **POST** | `/api/habits` | Tạo thói quen mới | `{ "name": "...", "description": "..." }` |
| **GET** | `/api/habits/:id` | Lấy chi tiết 1 thói quen | Trống |
| **PUT** | `/api/habits/:id` | Sửa thói quen | `{ "name": "...", "description": "..." }` |
| **DELETE**| `/api/habits/:id` | Xóa thói quen | Trống |
| **POST** | `/api/habits/:id/checkin` | Check-in thói quen | Trống (Trả về lỗi 400 nếu ngày đó đã check-in) |

*Lưu ý: Log lỗi hệ thống hiện đang được ghi vào file `backend-error.log`.*

---

## 2. Dành cho Ngô Đức Nhân (DevOps Engineer)

- **Ngôn ngữ:** Node.js (phiên bản 18 hoặc 20 đều được).
- **Lệnh cài đặt:** `npm install`
- **Lệnh chạy App:** `npm start` (đã gắn lệnh `node index.js` vào package.json).
- **Cổng (Port) mặc định:** `3000` (có thể config qua biến môi trường `PORT`).

Nhiệm vụ của bạn là viết `Dockerfile` bọc cái app Node.js này lại và đẩy lên qua GitHub Actions.

---

## 3. Dành cho Võ Trọng Hiếu (Infrastructure + QA)

Khi Deploy lên server, bạn nhớ cấu hình **3 Biến môi trường (Environment Variables)** sau trong phần cài đặt của Server/Hosting:

```env
PORT=3000
SUPABASE_URL=https://<your_supabase_project>.supabase.co
SUPABASE_KEY=<your_supabase_service_role_key>
```
*Lưu ý: Database Supabase đã được setup xong, bạn lấy KEY trong nhóm nhé.*

Về phần QA: Bạn có thể thử cố tình nhập sai Key của Supabase, hoặc cố tình gọi check-in 2 lần để tạo **Incident (Lỗi)** và chụp màn hình Postman / Terminal lại viết báo cáo nhé!
