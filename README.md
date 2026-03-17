# Movie Ticket Booking Management System

## Mục đích của dự án

Hệ thống quản lý đặt vé xem phim (Movie Ticket Booking Management System) là một ứng dụng desktop được phát triển bằng JavaFX nhằm cung cấp giải pháp toàn diện cho việc quản lý và đặt vé xem phim. Dự án này được thiết kế để phục vụ cả người dùng cuối (khách hàng) và quản trị viên (admin), giúp tối ưu hóa quy trình đặt vé, quản lý phim, và xử lý thanh toán một cách hiệu quả.

Mục đích chính:
- Cung cấp nền tảng dễ sử dụng cho khách hàng đặt vé xem phim trực tuyến.
- Giúp quản trị viên quản lý phim, suất chiếu, và dữ liệu người dùng.
- Đảm bảo trải nghiệm người dùng mượt mà với giao diện thân thiện.
- Tích hợp các tính năng bảo mật như xác thực email và mã hóa dữ liệu.

## Tính năng chính

### Cho người dùng (Application Module):
- **Đăng ký và Đăng nhập**: Tạo tài khoản mới với xác thực email, đăng nhập an toàn.
- **Quên mật khẩu**: Khôi phục mật khẩu qua email.
- **Xem danh sách phim**: Duyệt và tìm kiếm phim theo thể loại, thời gian.
- **Chọn ghế**: Chọn vị trí ghế trong rạp với giao diện trực quan.
- **Thanh toán**: Hỗ trợ nhiều phương thức thanh toán (thẻ tín dụng, UPI, ngân hàng).
- **Tải vé**: Xuất vé dưới dạng PDF sau khi đặt thành công.
- **Quản lý hồ sơ**: Cập nhật thông tin cá nhân và xem lịch sử đặt vé.

### Cho quản trị viên (Manager Module):
- **Quản lý phim**: Thêm, sửa, xóa thông tin phim và suất chiếu.
- **Quản lý người dùng**: Xem danh sách người dùng, thống kê.
- **Thống kê và báo cáo**: Phân tích doanh thu, số lượng vé bán.
- **Dashboard**: Giao diện tổng quan với biểu đồ và số liệu.

### Tính năng chung:
- **Bảo mật**: Mã hóa mật khẩu, xác thực email.
- **Cơ sở dữ liệu**: Lưu trữ dữ liệu người dùng, phim, và đặt vé bằng SQLite.
- **Gửi email**: Thông báo đặt vé và khôi phục mật khẩu.

## Công nghệ sử dụng

- **Ngôn ngữ lập trình**: Java 17 (OpenJDK)
- **Framework GUI**: JavaFX 21 (cho giao diện người dùng)
- **Cơ sở dữ liệu**: SQLite (nhẹ nhàng, không cần server)
- **Thư viện bổ sung**:
  - Gson: Xử lý JSON cho dữ liệu phim và người dùng.
  - JavaMail: Gửi email tự động.
  - SQLite JDBC: Kết nối và thao tác với cơ sở dữ liệu.
- **Công cụ build**: Eclipse IDE (dựa trên .project và .classpath), có thể sử dụng Maven/Gradle.
- **Hệ điều hành**: Windows (tương thích với Linux/Mac qua JavaFX).

## Cấu trúc thư mục

```
OOP-20242-Cinema/
├── .classpath                 # Cấu hình classpath cho Eclipse
├── .project                   # Cấu hình dự án Eclipse
├── .settings/                 # Cài đặt Eclipse
├── bin/                       # Thư mục chứa file .class đã biên dịch
│   ├── application/           # Class của module application
│   │   ├── controllers/       # Controller cho các màn hình
│   │   ├── css/               # File CSS cho styling
│   │   ├── fxml/              # File FXML cho giao diện
│   │   ├── lib/               # Thư viện JAR (SQLite, Gson, etc.)
│   │   ├── resources/         # Tài nguyên (icon, hình ảnh)
│   │   └── utils/             # Utility classes (DB, Email, JSON)
│   └── manager/               # Class của module manager (admin)
│       ├── images/            # Hình ảnh cho admin
│       ├── model/             # Model classes
│       ├── util/              # Utility cho manager
│       └── view/              # View classes
├── build.fxbuild              # Cấu hình build JavaFX
├── README.md                  # Tài liệu dự án (file này)
├── src/                       # Mã nguồn
│   ├── application/           # Module chính cho người dùng
│   │   ├── Main.java          # Entry point của ứng dụng
│   │   ├── controllers/       # Controller classes (Login, Dashboard, etc.)
│   │   ├── css/               # Stylesheets
│   │   ├── database/          # Dữ liệu mẫu (JSON files)
│   │   ├── fxml/              # FXML files
│   │   ├── lib/               # Dependencies
│   │   ├── resources/         # Resources
│   │   └── utils/             # Utilities
│   ├── manager/               # Module quản trị
│   │   ├── DashboardAdminController.java
│   │   ├── MainApp.java       # Entry point cho admin
│   │   ├── images/
│   │   ├── model/
│   │   ├── util/
│   │   └── view/
│   ├── META-INF/              # Manifest
│   └── module-info.java       # Module definition
└── .gitignore                 # Git ignore rules
```

## Kế hoạch phát triển

### Giai đoạn 1: Hoàn thiện tính năng cơ bản (Đã hoàn thành)
- Phát triển giao diện đăng nhập/đăng ký.
- Tích hợp cơ sở dữ liệu SQLite.
- Triển khai chức năng đặt vé và thanh toán.
- Thêm module quản trị cơ bản.

### Giai đoạn 2: Cải tiến và mở rộng (Đang phát triển)
- Tối ưu hóa hiệu suất và UI/UX.
- Thêm tính năng thông báo real-time (WebSocket hoặc polling).
- Hỗ trợ đa ngôn ngữ (i18n).
- Tích hợp API bên thứ ba cho thanh toán (Stripe, PayPal).

### Giai đoạn 3: Triển khai và bảo trì (Tương lai)
- Chuyển sang web app hoặc mobile app.
- Triển khai trên cloud (Azure, AWS).
- Thêm tính năng AI cho đề xuất phim.
- Bảo mật nâng cao (OAuth, JWT).

### Roadmap chi tiết:
- **Tháng 1-2**: Hoàn thiện UI và testing.
- **Tháng 3**: Tích hợp CI/CD.
- **Tháng 4**: Phát hành phiên bản beta.
- **Tháng 5+**: Thu thập feedback và cải tiến.

## Cách chạy dự án

### Yêu cầu hệ thống:
- Java 17+ (OpenJDK)
- JavaFX 21+ (hoặc JRE 8 với JavaFX tích hợp)

### Bước chạy:
1. Clone repository: `git clone https://github.com/HungDn5105/OPP-Cinema.git`
2. Mở trong Eclipse hoặc IDE hỗ trợ JavaFX.
3. Import project và resolve dependencies.
4. Chạy `application.Main` cho user app hoặc `manager.MainApp` cho admin.

### Build và Run từ command line:
- Biên dịch: `javac -cp "lib/*" src/**/*.java -d bin`
- Chạy: `java -cp "bin;lib/*" --module-path /path/to/javafx/lib --add-modules javafx.controls,javafx.fxml application.Main`

## Đóng góp

Chào mừng đóng góp! Vui lòng tạo issue hoặc pull request trên GitHub.

## Giấy phép

Xem LICENSE file để biết thêm chi tiết.

## Liên hệ

- Tác giả: [Tên tác giả]
- Email: [daonhathung2005@gmail.com]
- GitHub: https://github.com/HungDn5105/OPP-Cinema
