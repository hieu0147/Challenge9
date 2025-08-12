# Library API

## Mô tả
API quản lý thư viện cho phép quản lý người dùng, sách, danh mục, mượn/trả sách và xác thực OTP qua email. Hệ thống hỗ trợ phân quyền, xác thực JWT, kiểm tra dữ liệu đầu vào và tài liệu hóa API với Swagger.

## Tính năng chính
- Đăng ký, xác thực OTP, đăng nhập người dùng
- Quản lý sách (CRUD, phân trang)
- Quản lý danh mục sách (CRUD)
- Quản lý mượn/trả sách, báo cáo sách đang mượn
- Phân quyền người dùng (admin, user)
- Xác thực JWT cho các API bảo vệ
- Gửi email OTP xác thực tài khoản
- Kiểm tra dữ liệu đầu vào với Joi
- Tài liệu hóa API với Swagger UI

## Công nghệ sử dụng
- Node.js, Express.js
- MongoDB, Mongoose
- TypeScript
- JWT, Bcrypt
- Nodemailer
- Joi, express-validator
- Swagger UI

## Cài đặt
1. Clone dự án:
   ```bash
   git clone https://gitlab.com/lekhahieu03/challenge_9.git
   cd challenge_9/library-api
   ```
2. Cài đặt dependencies:
   ```bash
   npm install
   ```
3. Tạo file `.env` với nội dung mẫu:
   ```env
   MONGODB_URI=mongodb://localhost:27017/library
   EMAIL_USER=your_gmail@gmail.com
   EMAIL_PASS=your_gmail_app_password
   JWT_SECRET=your_jwt_secret
   PORT=3000
   ```

## Chạy ứng dụng
- Chạy ở chế độ phát triển:
  ```bash
  npm run dev
  ```
- Build và chạy production:
  ```bash
  npm run build
  npm start
  ```

## Tài liệu API
- Truy cập Swagger UI tại: [http://localhost:3000/api-docs](http://localhost:3000/api-docs)

## Ví dụ API
### Đăng ký người dùng
```
POST /users
{
  "name": "Nguyen Van A",
  "email": "a@gmail.com",
  "password": "123456",
  "role": "user"
}
```

### Đăng nhập
```
POST /auth/login
{
  "email": "a@gmail.com",
  "password": "123456"
}
```

### Gửi và xác thực OTP
```
POST /users/{id}/send-otp
POST /users/{id}/verify-otp
```

### Quản lý sách, danh mục, mượn trả
- Xem chi tiết tại Swagger UI hoặc các route `/books`, `/categories`, `/borrows`

## Đóng góp
Mọi đóng góp, báo lỗi hoặc đề xuất vui lòng tạo issue hoặc merge request.

## License
MIT 