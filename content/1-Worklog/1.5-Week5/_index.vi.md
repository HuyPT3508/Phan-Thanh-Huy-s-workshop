---
title: "Tuần 5: Tính năng Nâng cao (Real-time)"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu Tuần 5

* Triển khai các tính năng nâng cao đòi hỏi tính đồng bộ dữ liệu cao.
* Giải quyết bài toán Race Condition (Xung đột dữ liệu) khi nhiều người cùng đặt một ghế.
* Áp dụng công nghệ WebSockets để cập nhật giao diện thời gian thực (Real-time).

### Các công việc đã thực hiện

1. **Giải quyết bài toán Khóa ghế (Seat Locking):**
   * Tích hợp **Amazon DynamoDB** (mô phỏng ở local thông qua NoSQL) để lưu trữ trạng thái khóa ghế tạm thời với thời gian sống (TTL) là 5 phút.
   * Nếu user không thanh toán sau 5 phút, ghế tự động được nhả ra cho người khác chọn.
   * Đảm bảo tính nhất quán dữ liệu (ACID) khi ghi vé chính thức vào PostgreSQL.
2. **Tích hợp Socket.IO (Real-time):**
   * Cài đặt thư viện Socket.IO trên Node.js Backend.
   * Xây dựng luồng kết nối: Khi Khách hàng A bấm chọn 1 ghế, tín hiệu được bắn lên Server, Server phát Broadcast ngay lập tức cho tất cả Khách hàng B, C, D đang xem cùng suất chiếu đó để đổi màu ghế thành "Đang giữ" (Màu xám).
3. **Phát triển luồng Thanh toán & Vé QR:**
   * Tích hợp mã hóa thông tin đơn hàng thành mã QR code vé điện tử.
   * Hoàn thiện lịch sử mua vé trong trang cá nhân của Khách hàng.

### Kết quả đạt được

* Xử lý triệt để lỗi 2 người cùng đặt 1 ghế.
* Giao diện chọn ghế phản hồi ngay lập tức (real-time) với các thao tác của người dùng khác.
