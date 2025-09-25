# Thiết lập môi trường Local

## 1. Mục tiêu

Thiết lập môi trường **local** để phát triển dự án, đảm bảo mỗi thành viên có thể chạy dự án trên máy cá nhân một cách đồng bộ, nhất quán và dễ dàng.

---

## 2. Yêu cầu hệ thống

- **Java**: JDK 21 (hoặc phiên bản theo quy định của team)
- **Node.js**: >= 18.x
- **npm** hoặc **yarn**
- **MySQL**: >= 8.0
- **Git**: >= 2.x
- IDE khuyến nghị:
  - Backend: IntelliJ IDEA
  - Frontend: VSCode

---

## 3. Cấu trúc dự án

```
project-root/
├── backend/ # Spring Boot project
├── frontend/ # Vue.js project
└── docs/ # Tài liệu
```

## 4. Thiết lập Backend (Spring Boot)

1. **Clone project**
   ```bash
   git clone <repository-url>
   cd backend
   ```
2. **Tạo file cấu hình application-local.yml**

    ```bash
    spring:
    datasource:
        url: jdbc:mysql://localhost:3306/project_db?useSSL=false&serverTimezone=UTC
        username: app_user
        password: app_password
    jpa:
        hibernate:
        ddl-auto: update
        show-sql: true
    server:
    port: 8080
    ```
3. Chạy ứng dụng:
    ```bash
    ./mvnw spring-boot:run
    hoặc 
    chạy trực tiếp trong IDE
    ```
## 5. Thiết lập Frontend (VueJS)
1. **Cài đặt dependency**
    ```bash
    cd frontend
    npm install
    ```
2. **Tạo file .env.local**
    ```bash
    VITE_API_URL=http://localhost:8080/api
    ```
3. **Chạy ứng dụng**
    ```bash
    npm run dev
    ```
    Truy cập tại: http://localhost:5173
### 6. Database
- Tạo database
    ```bash
    CREATE DATABASE project_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
    ```
- Tạo user riêng cho ứng dụng
    ```bash
        CREATE USER 'app_user'@'localhost' IDENTIFIED BY 'app_password';
        GRANT ALL PRIVILEGES ON project_db.* TO 'app_user'@'localhost';
        FLUSH PRIVILEGES;
    ```

## 7. Git Workflow
- Branch chính: main
- Branch phát triển: develop
- Tạo nhánh tính năng từ develop:
    ```bash
    git checkout develop
    git pull origin develop
    git checkout -b feature/<feature-name>
    ```
### 8. Ghi chú
- Luôn chạy backend trước rồi mới chạy frontend.