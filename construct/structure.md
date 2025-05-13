### Cấu trúc các folder của 1 dự án Laravel Version 11
    1. app/ - Logic chính của ứng dụng 

**Đây là nơi chứa phần lớn code của ta: controller, middleware, service provider, logic nghiệp vụ,..**
- Đây là "bộ não" của Laravel: hầu hết các class ta viết sẽ nằm ở đây.
- Các lớp được tự động nạp nhờ Composer PSR-4 autoload.


    2. bootstrap/ -  Khởi tạo ứng dụng

**Chứa file app.php – nơi Laravel được khởi tạo và cấu hình lúc bắt đầu.**
- bootstrap/app.php sẽ load app Laravel, cấu hình autoload, chuẩn bị app để xử lý request.
- Thư mục bootstrap/cache/: chứa file cache đã biên dịch (route, config,...), giúp tăng tốc độ.
- Ít đụng tới, nhưng rất quan trọng để app chạy được.


    3. config/ - Cấu hình hệ thống

**Chứa tất cả file cấu hình: database, cache, mail, queue, app, v.v.**

- Ví dụ: config/database.php cho cấu hình DB.
- Laravel sử dụng giá trị trong .env, sau đó inject vào các file trong đây.
- Ta thường sửa khi cần cấu hình môi trường hoặc dịch vụ.


    4. database/ - Cấu trúc và dữ liệu

**Tổ chức các script liên quan đến cơ sở dữ liệu.**

- migrations/: định nghĩa cấu trúc bảng (table schema).
- seeders/: dữ liệu mẫu
- factories/: tạo dữ liệu giả cho testing

=> Làm việc thường xuyên khi ta quản lý schema và dữ liệu.


    5. public/ – Entry point của web server

**Thư mục duy nhất web server (Apache/Nginx) có quyền truy cập**

- Chứa index.php → tất cả request HTTP bắt đầu từ đây.
- Chứa các file tĩnh: hình ảnh, JS, CSS đã biên dịch, favicon,...

=> Không bao giờ đặt code ứng dụng ở đây.


    6. resources/ – Giao diện người dùng (UI)

**Nơi chứa Blade templates, CSS/JS chưa biên dịch.**
- views/: chứa file .blade.php.
- js/, css/: dùng khi tích hợp Vite hoặc Webpack.

=> Thường xuyên chỉnh sửa khi làm UI.


    7. routes/ – Khai báo đường dẫn (routes)
**Nơi định nghĩa các route (web/api) và liên kết với controller.**
- web.php: routes cho giao diện web.
- api.php: routes cho API RESTful.

=> Ta sẽ cần phải thao tác nhiều tại đây khi viết ứng dụng.

    8. storage/ – Lưu trữ dữ liệu runtime

**Laravel sử dụng thư mục này để xử lý nội dung tạm thời.**
- Sử dụng cho: 
- Cache (route, config,...)
- Log file
- Session
- Tập tin do người dùng upload

=> Không nên commit nội dung thư mục này lên Git (trừ storage/app/public)

    9. tests/ – Kiểm thử (Testing)

**Chứa các file kiểm thử đơn vị (unit test) và tính năng (feature test).**
- Laravel dùng PHPUnit để chạy test.
- Cấu trúc test gọn và dễ mở rộng.

=> Rất quan trọng trong team lớn hoặc dự án dài hạn.

### Ngoài ra còn có các folder khác tuỳ vào phiên bản, có thể khởi tạo sẵn hoặc tạo thủ công.
    10. lang/ – Đa ngôn ngữ (i18n)
**Chứa các file dịch cho giao diện, thông báo lỗi, v.v.**
- Ví dụ: lang/en/validation.php chứa thông báo lỗi tiếng Anh.
- Có thể tạo lang/vi để hỗ trợ tiếng Việt.

=> Cần thiết nếu ta làm ứng dụng đa ngôn ngữ.

## 📌 Kết luận

| Thư mục      | Mục đích chính                  | Mức độ sử dụng |
|--------------|----------------------------------|----------------|
| `app/`       | Chứa logic chính                | Cao            |
| `bootstrap/` | Khởi tạo ứng dụng               | Thấp           |
| `config/`    | Cấu hình các dịch vụ            | Trung bình     |
| `database/`  | Migration, seed, factory        | Trung bình     |
| `lang/`      | Đa ngôn ngữ                     | Thấp           |
| `public/`    | Web entry point, file tĩnh      | Thấp           |
| `resources/` | UI: blade, CSS, JS              | Cao            |
| `routes/`    | Định nghĩa các route            | Cao            |
| `storage/`   | Cache, log, file upload         | Thấp           |
| `tests/`     | Kiểm thử code                   | Thấp           |
