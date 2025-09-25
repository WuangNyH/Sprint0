# 🔧 Công cụ Backend (Java + Spring Boot)

1. **JDK 21**

   - Cài bản **Oracle JDK 21** hoặc **OpenJDK 21**. [Download](https://www.oracle.com/java/technologies/downloads/#java21)
   - Kiểm tra sau khi cài:
     ```bash
     java -version
     javac -version
     ```

2. **IntelliJ IDEA (Community/Ultimate)**

   - IDE mạnh mẽ cho Java, Spring Boot.
   - Plugin cần thiết:

     - Lombok
     - MapStruct Support
     - Spring boot JPA
     - Spring Web

3. **Build Tool**

   - Maven hoặc Gradle (tuỳ dự án).
   - Kiểm tra:

     ```bash
     mvn -v
     gradle -v
     ```

---

# 🖥️ Công cụ Frontend (VueJS)

1. **Node.js v20**

   - Cài từ [nodejs.org](https://nodejs.org/en/download) hoặc **nvm** (Node Version Manager) để quản lý nhiều phiên bản.
   - Kiểm tra:

     ```bash
     node -v
     npm -v
     ```

   - Cài **Yarn** hoặc **pnpm** nếu muốn build nhanh hơn:

     ```bash
     npm install -g yarn
     npm install -g pnpm
     ```

2. **Vue CLI / Vite** (Vite thường dùng cho Vue 3, nhanh hơn Vue CLI).

   - Cài Vite:

     ```bash
     npm create vite@latest
     ```

   - Hoặc Vue CLI:

     ```bash
     npm install -g @vue/cli
     vue --version
     ```

3. **IDE/Editor**

   - **Visual Studio Code** (phù hợp cho Vue + JS/TS).
   - Extensions cần có:

     - Vue Language Features (Volar)
     - ESLint
     - Prettier
     - TailwindCSS IntelliSense (nếu dùng Tailwind)

---

# 🌐 Công cụ Quản lý Source Code

1. **Git**

   - Cài từ [git-scm.com](https://git-scm.com/downloads).
   - Kiểm tra:

     ```bash
     git --version
     ```

   - Cấu hình cơ bản:

     ```bash
     git config --global user.name "KayZ"
     git config --global user.email "your_email@example.com"
     ```

2. **GitHub/GitLab/Bitbucket**

   - Tạo account để lưu trữ và cộng tác code.
   - Cài thêm **GitHub CLI** (tuỳ chọn).

---

# 🐳 Công cụ DevOps & Môi trường

1. **Docker**

   - Cài **Docker Engine** + **Docker Compose**.
   - Kiểm tra:

     ```bash
     docker -v
     docker compose version
     ```

   - Dùng để chạy DB (PostgreSQL, MySQL, Redis), deploy service.

2. **Postman hoặc Insomnia**

   - Test API backend.

3. **DBeaver hoặc pgAdmin**

   - Quản lý database (PostgreSQL/MySQL).
