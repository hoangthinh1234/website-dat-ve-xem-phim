![CINEMEET Logo](./public/images/branding/logos/logo-w.png)

# Giới thiệu dự án

**CINEMEET** là một hệ thống đặt vé xem phim được phát triển bằng **Laravel 8**.  
Hệ thống có các chức năng như: phân quyền người dùng, xác thực đăng nhập, đặt vé tự động và nhiều tính năng khác.

Xem bản demo trực tiếp **[tại đây](https://cinemat.zeiadmohamed.dev)**.

## Những gì tôi học được

-   Kiến thức cơ bản về Routing
-   Kiến trúc MVC
-   Ngôn ngữ template Blade
-   Middleware
-   Cơ bản về xác thực và phân quyền
-   Cơ sở dữ liệu quan hệ (MySQL)
-   Migration cơ sở dữ liệu
-   Eloquent ORM
-   Các thao tác CRUD với cơ sở dữ liệu
-   HTML, CSS, JavaScript
-   Alpine.js
-   Upload tệp
-   Tìm kiếm và lọc dữ liệu trong Model

## Cách sử dụng

Bạn có thể truy cập website **[tại đây](https://cinemat.zeiadmohamed.dev)**.  
Website đã có sẵn một số phim, bạn có thể đăng nhập với vai trò **Manager** để chỉnh sửa hoặc tạo phim mới.  
**[Đăng nhập](https://cinemat.zeiadmohamed.dev/login)**

> Lưu ý: Website sẽ tự động reset dữ liệu sau mỗi 30 phút.

### Tài khoản mẫu

| Vai trò người dùng | Email                         | Mật khẩu    |
| ------------------ | ----------------------------- | ----------- |
| Admin              | admin&#64;cinemeet&#46;com    | adminpass   |
| Manager            | manager&#64;cinemeet&#46;com  | managerpass |
| Customer           | customer&#64;cinemeet&#46;com | customerpass |

<br>

---

<br>

## Hướng dẫn cài đặt

<br>

1. Clone repository bằng cách chạy lệnh sau trong terminal hoặc command prompt:
    ```bash
    git clone https://github.com/ziadabdo98/Cinemat.git
    ```
2. Di chuyển vào thư mục project:
    ```bash
    cd Cinemat
    ```
3. Cài đặt các thư viện cần thiết bằng Composer (đảm bảo máy đã cài Composer):
    ```bash
    composer install
    ```
4. Tạo file cấu hình môi trường bằng cách sao chép `.env.example` thành `.env` và nhập thông tin database:
    ```bash
    cp .env.example .env
    ```
5. Tạo application key:
    ```bash
    php artisan key:generate
    ```
6. Cấu hình file `.env`. Mở file `.env` và thiết lập các thông tin cần thiết như database và các cấu hình của ứng dụng.
7. Chạy migration để tạo các bảng dữ liệu:
    ```bash
    php artisan migrate
    ```
8. (Tùy chọn) Tạo dữ liệu mẫu gồm 20 phim, suất chiếu, người dùng và danh mục:
    ```bash
    php artisan db:seed
    ```
9. Tạo symbolic link từ `public/storage` đến `storage/app/public`:
    ```bash
    php artisan storage:link
    ```
    Ứng dụng Laravel sẽ có thể truy cập tại URL (thường là http://localhost:8000).
10. Cuối cùng, chạy server phát triển:
    ```bash
    php artisan serve
    ```
    Ứng dụng Laravel sẽ có thể truy cập tại URL (thường là http://localhost:8000).

<br>

## Phân quyền người dùng

<br>

**Quản trị viên (Administrator):**

-   Quản lý việc tạo người dùng và phân quyền hệ thống
-   Duyệt yêu cầu trở thành Manager
-   Có thể xóa người dùng hiện có

**Quản lý (Manager):**

-   Quản lý, tạo mới và chỉnh sửa thông tin phim
-   Quản lý, tạo mới và chỉnh sửa suất chiếu
-   Cập nhật thông tin như: tiêu đề phim, ngày chiếu, giờ bắt đầu và kết thúc, phòng chiếu, hình ảnh poster
-   Xem tổng trạng thái ghế của từng suất chiếu (trống / đã đặt)

**Khách hàng (Customer):**

-   Người dùng đã đăng ký và cung cấp thông tin cá nhân
-   Có thể đặt vé xem phim
-   Có thể đặt bất kỳ số lượng vé nào cho các suất chiếu không bị trùng thời gian

**Khách (Guest):**

-   Người dùng chưa đăng nhập
-   Có thể xem thông tin phim đang chiếu
-   Có thể đăng nhập hoặc đăng ký tài khoản
-   Không thể đặt vé
