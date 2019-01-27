# Các thiết lập cơ bản
## Thiết lập quyền ghi cho một số thư mục trong dự án
```
# Nếu sử dụng Nginx
chown -R nginx:nginx storage
chown -R nginx:nginx bootstrap/cache
# Nếu sử dụng Apache
chown -R apache:apache storage
chown -R apache:apache bootstrap/cache
```
## Copy file .env và tạo application key
Quá trình cài đặt đã tự động sinh ra application key, nếu bạn copy mã nguồn ở đâu đó về, cần tạo application key lại bằng lệnh 
```
php artisan key:generate
Application key [base64:bib6Gi4iQ/sI3WTq8L7baYcD4wRZrd7dUNOoTOENsUg=] set successfully.
```
Chú ý, nếu thư mục gốc chưa có file .env là file chứa các thiết lập môi trường thực hiện copy từ file .env.example sang .env trước khi thực hiện lệnh tạo lại application key ở trên. 
```
cp .env.example .env
```
## Thiết lập địa phương và múi giờ
Cấu hình múi giờ cũng như địa phương hoạt động của ứng dụng trong config/app.php 
```
    /*
    |--------------------------------------------------------------------------
    | Application Timezone
    |--------------------------------------------------------------------------
    |
    | Here you may specify the default timezone for your application, which
    | will be used by the PHP date and date-time functions. We have gone
    | ahead and set this to a sensible default for you out of the box.
    |
    */

    'timezone' => 'Asia/Saigon',

    /*
    |--------------------------------------------------------------------------
    | Application Locale Configuration
    |--------------------------------------------------------------------------
    |
    | The application locale determines the default locale that will be used
    | by the translation service provider. You are free to set this value
    | to any of the locales which will be supported by the application.
    |
    */

    'locale' => 'vn',
```
# Các thiết lập biến môi trường
