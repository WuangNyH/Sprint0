# 📌 Thiết lập Phân quyền và Bảo mật cho các thành viên:

### 1. Quyền truy cập mã nguồn
- Sử dụng Git (GitHub).  
- Tất cả thành viên có quyền **read/write** repository.  
- Chỉ thành viên được chỉ định (Lead/Reviewer) có quyền **merge vào branch chính** (`develop`/`main`).  
- Workflow: mỗi tính năng/bugfix phát triển trên **branch riêng** và mở **Pull Request (PR)** để review trước khi merge.  

### 2. Quyền triển khai (CI/CD)
- **Local**: mỗi dev tự chạy và test code.  
- **Staging**: chỉ Lead/DevOps được trigger deploy.  
- **Production**: chỉ Lead/DevOps có quyền deploy.  

### 3. Quản lý Database
- Tài khoản DB môi trường dev/test chỉ có quyền **SELECT, INSERT, UPDATE, DELETE**.  
- Chỉ Lead Developer có quyền **ALTER, DROP, CREATE**.  
- Không sử dụng tài khoản `root` cho ứng dụng.

### 4. Quản lý Secrets & Config
- **Mật khẩu và secrets** được quản lý bằng Environment Variables hoặc Vault.
- Dùng **HTTPS (SSL/TLS)** cho môi trường staging và production.
- Cấu hình **CORS** để hạn chế nguồn gọi API.
- Ghi **audit log** khi có thao tác quan trọng (deploy, thay đổi schema DB, chỉnh sửa cấu hình).