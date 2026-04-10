# 🎓 Đồ án: Hệ thống Quản lý Ý tưởng Sinh viên (Unildeas Portal)

**Môn học:** COMP1640  
**Thực hiện bởi:** Nhóm KH  

Kính chào Thầy/Cô, dưới đây là tài liệu hướng dẫn chi tiết để Thầy/Cô có thể dễ dàng truy cập, trải nghiệm các chức năng và chấm điểm đồ án của nhóm em.

---

## 🌐 1. Trải nghiệm trực tiếp trên Website (Live Demo)

Để thuận tiện nhất cho việc chấm điểm mà không cần cài đặt môi trường phức tạp, nhóm em đã triển khai (deploy) toàn bộ hệ thống (Frontend & API Backend) lên server thực tế. Thầy/Cô có thể truy cập trực tiếp tại đường link sau:

👉 **[https://mmideas.infinityfree.me/login.html](https://mmideas.infinityfree.me/login.html)**

*(Lưu ý nhỏ: Vì nhóm sử dụng máy chủ Hosting giáo dục miễn phí, đôi khi ở lần truy cập đầu tiên hoặc upload file hệ thống sẽ phản hồi chậm mất 3-5 giây. Kính mong Thầy/Cô thông cảm chờ đợi một chút ạ).*

---

## 🔑 2. Tài khoản Kiểm thử (Test Accounts)

Nhóm đã tạo sẵn các tài khoản với từng vai trò riêng biệt để Thầy/Cô tiện test phân quyền. 
*(Ghi chú: Thầy/Cô có thể sử dụng biểu tượng 👁️ ở ô mật khẩu để xem rõ password khi nhập).*

| Vai trò (Role) | Chức năng chính | Email đăng nhập | Mật khẩu |
| :--- | :--- | :--- | :--- |
| **Admin** | Quản lý tài khoản, xem thống kê | `admin@univ.edu` | `123456` |
| **Staff** | Viết bài, nộp ý tưởng, upload file | `staffit@univ.edu` | `123456` |
| **QA Coordinator**| Quản lý danh mục, download file CSV| `qac@univ.edu` | `123456` |
| **QA Manager** | Duyệt ý tưởng, xem Dashboard | `qam@univ.edu` | `123456` |


---

## 🚀 3. Luồng tính năng cốt lõi cần Kiểm tra

Để đánh giá toàn diện hệ thống, Thầy/Cô có thể trải nghiệm theo luồng (flow) sau:

1. **Test nộp bài (Staff):** Đăng nhập bằng tài khoản Staff -> Viết một ý tưởng mới -> Đính kèm một file ảnh/tài liệu -> Nhấn Submit. (Hệ thống đã được cấu hình cấp quyền thư mục để lưu trữ file an toàn).
2. **Test tương tác:** Staff khác có thể xem ý tưởng, Like (Thumbs up) hoặc Thêm bình luận (Comment).
3. **Test quản lý (QA Coordinator):** Đăng nhập bằng tài khoản QAC -> Tải toàn bộ ý tưởng hoặc file đính kèm dưới dạng `.zip` hoặc `.csv`.
4. **Test thống kê (QA Manager):** Đăng nhập bằng tài khoản QAM -> Truy cập trang Dashboard để xem biểu đồ thống kê trực quan.

---

## 💻 4. Hướng dẫn chạy Local (Phương án Dự phòng)

Trong trường hợp server live của InfinityFree được bảo trì hoặc gặp sự cố mạng, Thầy/Cô có thể chạy trực tiếp source code trên máy tính cá nhân theo các bước tiêu chuẩn của Laravel:

**Yêu cầu hệ thống:** PHP >= 8.1, Composer, MySQL/XAMPP.

Bước 1: Cài đặt thư viện Backend

Mở Terminal tại thư mục gốc của dự án và chạy lệnh:

composer install

Bước 2: Cấu hình Môi trường

Copy file .env.example thành .env. Sau đó mở XAMPP, tạo một database mới tên là nhomkh và cập nhật thông tin vào file .env:
   DB_CONNECTION=mysql

   DB_HOST=127.0.0.1

   DB_PORT=3306

   DB_DATABASE=nhomkh

   DB_USERNAME=root

   DB_PASSWORD=

Bước 3: Khởi tạo dữ liệu

Chạy các lệnh sau để tạo Key, cấp quyền thư mục ảnh và nạp dữ liệu mẫu:
   php artisan key:generate

   php artisan storage:link

   php artisan migrate --seed


Bước 4: Khởi động Server
   php artisan serve


Sau đó, Thầy/Cô mở trình duyệt và truy cập vào: http://127.0.0.1:8000/login.html để trải nghiệm hệ thống Local.
Nhóm KH xin chân thành cảm ơn Thầy/Cô đã dành thời gian xem xét và đánh giá đồ án của nhóm!