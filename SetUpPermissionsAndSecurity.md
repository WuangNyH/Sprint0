# 📌 Thiết lập Phân quyền và Bảo mật - Hệ thống Quản lý Học viên

## 🔑 Vai trò trong hệ thống

### 1. Admin
- Quản trị toàn bộ hệ thống
- Quản lý tài khoản (thêm/sửa/xóa user)
- Quản lý dữ liệu (học viên, giảng viên, giáo vụ, lớp học)
- Quản lý phân quyền

### 2. Giảng viên (Teacher)
- Xem danh sách học viên của lớp mình
- Nhập điểm, nhận xét học viên
- Xem lịch dạy

### 3. Giáo vụ (Academic Affairs Officer)
- Quản lý lịch học, lịch thi
- Sắp xếp lớp học
- Theo dõi tình trạng học viên (điểm danh, kết quả)
- Hỗ trợ giảng viên trong việc tổ chức lớp

### 4. Học viên (Student)
- Xem thông tin cá nhân, lịch học, lịch thi
- Xem điểm và kết quả học tập
- Gửi feedback / yêu cầu hỗ trợ

---

## 🛡️ Cơ chế bảo mật

### 1. Xác thực (Authentication)
- Người dùng đăng nhập bằng **username + mật khẩu**
- Mật khẩu **hash bằng bcrypt** trước khi lưu vào DB.
- Sau khi đăng nhập thành công, hệ thống cấp **JWT (JSON Web Token)**
- JWT chứa thông tin: `user_id`, `role`

### 2. Phân quyền (Authorization)
- Dựa trên **RBAC (Role-Based Access Control)**
- Middleware kiểm tra **JWT** và **role** trước khi xử lý API

### 3. Bảo mật hệ thống
- Dùng **HTTPS (SSL/TLS)** để mã hóa truyền thống
- Cấu hình **HTTP Security Headers** (Spring Sercurity)
- **Giới hạn số lần đăng nhập sai** để chống brute force.
- **Chống SQL Injection, XSS** (dùng ORM (JPA/Hibernate) + escape input)
- **Giảm quyền DB user**: không dùng root, chỉ cấp quyền tối thiểu cần thiết.
- **Refresh Token**: tránh việc JWT hết hạn khiến người dùng phải login lại.
- **CORS**: cấu hình để chỉ frontend hợp lệ mới được gọi API.