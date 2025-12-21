# 📚 BookSaw - Hệ thống Bán Sách Online

Một ứng dụng web bán sách hoàn chỉnh được xây dựng bằng **PHP thuần**, **MySQL**, và **Bootstrap 5**. Hệ thống bao gồm quản lý người dùng, giỏ hàng, và xem dữ liệu từ cơ sở dữ liệu.

---

## ✨ Tính năng chính

### 🔐 Hệ thống Xác thực
- ✅ Đăng ký tài khoản mới
- ✅ Đăng nhập/Đăng xuất
- ✅ Quản lý session người dùng
- ✅ Mã hóa mật khẩu với `password_hash()`

### 🛒 Chức năng Giỏ hàng
- ✅ Thêm sách vào giỏ hàng
- ✅ Xóa sách khỏi giỏ hàng
- ✅ Chỉnh sửa số lượng
- ✅ Xem tổng tiền động
- ✅ Thanh toán (tạo đơn hàng)

### 📖 Hiển thị Dữ liệu từ Database
- ✅ Danh sách sách (phân trang, lọc theo thể loại)
- ✅ Sách nổi bật (featured)
- ✅ Sách bán chạy nhất (bestseller)
- ✅ Sách giảm giá (on sale)
- ✅ Bài viết blog
- ✅ Tác giả, thể loại, khách hàng, đơn hàng

### 📊 Trang Quản lý Dữ liệu
- ✅ Xem toàn bộ dữ liệu từ database
- ✅ Thống kê số lượng
- ✅ Giao diện tab dễ sử dụng

---

## 🚀 Yêu cầu Hệ thống

- **PHP**: 7.2+ (khuyến nghị 7.4+)
- **MySQL**: 5.7+ hoặc MariaDB 10.4+
- **Web Server**: WAMP, XAMPP, hoặc tương tự
- **Browser**: Chrome, Firefox, Safari, Edge (hỗ trợ ES6)

---

## 📥 Cài đặt

### Bước 1: Sao chép dự án
```bash
# Sao chép vào thư mục www của WAMP
cp -r Website_it_me C:\wamp\www\
```

### Bước 2: Import Database
```bash
# Mở phpMyAdmin hoặc MySQL client
# Import file: booksaw_db.sql
mysql -u root -p < booksaw_db.sql
```

Hoặc dùng phpMyAdmin:
1. Truy cập `http://localhost/phpmyadmin`
2. Tạo cơ sở dữ liệu `booksaw_db`
3. Import file `booksaw_db.sql`

### Bước 3: Cấu hình Database
Kiểm tra file `database.php`:
```php
private $host = "localhost";        // Địa chỉ host
private $username = "root";         // Username MySQL
private $password = "";             // Password MySQL
private $dbname = "booksaw_db";     // Tên database
```

### Bước 4: Khởi động ứng dụng
1. Bật WAMP/XAMPP
2. Truy cập: `http://localhost/Website_it_me`

---

## 📁 Cấu trúc Thư mục

```
Website_it_me/
├── index.php                 # Trang chủ (hiển thị sách, bài viết)
├── login.php                 # Trang đăng nhập
├── register.php              # Trang đăng ký
├── auth.php                  # Xử lý xác thực (login/logout/register)
├── cart.php                  # Xử lý giỏ hàng (add/remove/update)
├── cart_view.php             # Trang xem giỏ hàng
├── data_view.php             # Trang xem tất cả dữ liệu từ DB
├── database.php              # Kết nối & class Database
├── booksaw_db.sql            # File SQL để import database
├── css/
│   ├── style.css             # Stylesheet chính
│   ├── vendor.css            # Vendor CSS
│   └── normalize.css         # CSS chuẩn hóa
├── js/
│   ├── jquery-1.11.0.min.js  # jQuery
│   ├── modernizr.js          # Modernizr
│   ├── plugins.js            # Plugin JavaScript
│   ├── script.js             # Script chính
│   ├── slideNav.js           # Navigation slide
│   └── slideNav.min.js       # Navigation slide (minified)
├── images/                   # Thư mục ảnh
│   └── chocolat/             # Ảnh cho gallery
├── icomoon/                  # Icon font
├── LICENSE                   # Thông tin giấy phép
└── README.md                 # File này
```

---

## 🌐 Các trang chính

| URL | Mô tả |
|-----|-------|
| `/` hoặc `/index.php` | Trang chủ - Hiển thị sách nổi bật, phổ biến, bài viết |
| `/login.php` | Đăng nhập |
| `/register.php` | Đăng ký tài khoản |
| `/cart_view.php` | Xem giỏ hàng |
| `/data_view.php` | Xem tất cả dữ liệu từ database |

---

## 💾 Cấu trúc Database

### Bảng chính
- **books** - Danh sách sách
- **authors** - Danh sách tác giả
- **categories** - Danh sách thể loại
- **customers** - Danh sách khách hàng
- **orders** - Danh sách đơn hàng
- **order_items** - Chi tiết đơn hàng
- **posts** - Danh sách bài viết

---

## 🔧 Hướng dẫn Sử dụng

### Đăng ký & Đăng nhập
1. Truy cập `/register.php` để tạo tài khoản
2. Nhập email, mật khẩu, và tên đầy đủ
3. Sau đó đăng nhập tại `/login.php`

### Mua Sách
1. Tại trang chủ, click **"Add to Cart"** trên bất kỳ sách nào
2. Xem giỏ hàng tại `/cart_view.php`
3. Chỉnh sửa số lượng hoặc xóa sách
4. Click **"Thanh Toán"** để tạo đơn hàng

### Xem Dữ liệu
1. Truy cập `/data_view.php` để xem tất cả dữ liệu
2. Sử dụng các tab để xem từng loại dữ liệu
3. Xem thống kê tổng hợp ở cuối trang

---

## 🛠️ Tùy chỉnh & Phát triển

### Thêm Sách mới
```php
// Trong database.php hoặc bất kỳ file nào
$db = new Database();
$db->execute(
    "INSERT INTO books (title, author_id, category_id, price, cover_image) 
     VALUES (?, ?, ?, ?, ?)",
    ['Tên sách', 1, 1, 29.99, 'cover_name']
);
```

### Thay đổi Giao diện
- Chỉnh sửa `css/style.css` để thay đổi màu sắc, phông chữ
- Cập nhật `js/script.js` để thêm JavaScript mới

### Mở rộng Chức năng
- Thêm thanh tìm kiếm: sửa `index.php`
- Thêm review sách: tạo bảng `reviews` và code xử lý
- Thêm wishlist: tạo bảng `wishlists` và lưu vào session/DB

---

## 🔐 Bảo mật

✅ **Được bảo vệ:**
- Mật khẩu được mã hóa với `password_hash()` (bcrypt)
- Dữ liệu được escape với `htmlspecialchars()`
- Sử dụng prepared statements (mysqli)
- Session management bảo mật

⚠️ **Khuyến nghị thêm:**
- Thêm CSRF token cho form
- Validate input ở server-side
- Sử dụng HTTPS trên production
- Giới hạn rate-limiting cho login

---

## 📝 Ghi chú Quan trọng

- File `booksaw_db.sql` chứa dữ liệu mẫu (books, authors, categories, posts)
- Mỗi session lưu giỏ hàng trong `$_SESSION['cart']`
- Đơn hàng được lưu trong database table `orders` và `order_items`
- Các ảnh sách được lưu trong thư mục `images/`

---

## 🐛 Khắc phục Sự cố

### Lỗi: "Cannot connect to database"
- Kiểm tra port MySQL (mặc định 3307)
- Kiểm tra username/password trong `database.php`
- Đảm bảo MySQL đang chạy

### Lỗi: "File not found" khi view ảnh
- Kiểm tra tên file ảnh trong database
- Đảm bảo ảnh tồn tại trong thư mục `images/`

### Session không hoạt động
- Đảm bảo `session_start()` được gọi ở đầu file
- Kiểm tra session.save_path trong php.ini

---

## 📞 Liên hệ & Hỗ trợ

Để tìm hiểu thêm hoặc báo cáo lỗi, vui lòng kiểm tra:
- File `database.php` - kết nối database
- File `auth.php` - xác thực người dùng
- File `cart.php` - xử lý giỏ hàng

---

## 📄 Giấy phép

Xem file `LICENSE` để biết chi tiết về giấy phép của dự án.

---

**Phiên bản**: 1.0  
**Cập nhật**: 2025-12-21  
**Nhà phát triển**: BookSaw Team
