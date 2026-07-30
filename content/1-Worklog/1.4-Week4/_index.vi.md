---
title: "Tuần 4: Thiết lập & Code tính năng cơ bản"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu Tuần 4

* Khởi tạo dự án, thiết lập môi trường phát triển (Local Environment).
* Cải tiến (Refactor) source code cũ, làm sạch code và chuyển đổi sang cấu trúc chuẩn.
* Xây dựng các tính năng cốt lõi cơ bản: Đăng nhập, Xem danh sách phim.

### Các công việc đã thực hiện

1. **Thiết lập môi trường Local:**
   * Cài đặt Node.js, Express cho Backend.
   * Cài đặt PostgreSQL trên máy cá nhân để mô phỏng Database trước khi đẩy lên RDS.
   * Xây dựng Frontend cơ bản bằng HTML/CSS/JS thuần, không sử dụng framework nặng để dễ dàng tối ưu hóa khi đẩy lên S3.
2. **Refactor Code cũ:**
   * Loại bỏ các đoạn code dư thừa từ dự án mẫu ban đầu.
   * Viết lại các API query vào Database bằng tham số an toàn để chống SQL Injection.
   * Tái cấu trúc thư mục dự án: tách biệt `routes`, `controllers`, `config`.
3. **Phát triển tính năng cơ bản:**
   * Xây dựng API lấy danh sách Phim đang chiếu.
   * Xây dựng trang Quản trị (Admin) cơ bản để thêm/xóa/sửa phim.

### Kết quả đạt được

* Môi trường phát triển đã sẵn sàng.
* Frontend có thể kết nối với Backend Local và gọi API thành công.
* Sẵn sàng phát triển các tính năng phức tạp hơn vào tuần sau.
