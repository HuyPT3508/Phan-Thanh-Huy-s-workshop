---
title: "Tuần 6: Kiểm thử & Chuẩn bị Deploy"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu Tuần 6

* Kiểm thử toàn bộ hệ thống (End-to-End) trên môi trường Local để phát hiện lỗi.
* Hoàn thiện các luồng tính năng chưa ổn định (Fix bugs).
* Soạn thảo kế hoạch triển khai (Deployment Plan) lên môi trường Cloud (AWS).

### Các công việc đã thực hiện

1. **Kiểm thử và Fix Bug:**
   * Khắc phục lỗi Frontend không gửi đúng mức giá vé (GiaVe) khi khách hàng mua ghế VIP, IMAX xuống Backend.
   * Cải thiện UI/UX của trang Admin, thêm logo trường, tối ưu hóa các thông báo lỗi cho người dùng.
   * Xử lý luồng hoàn tiền: Giả lập kịch bản Admin xóa một bộ phim đang có người mua vé, viết trigger để tự động gửi thông báo qua Email.
2. **Chuẩn bị hạ tầng AWS:**
   * Tính toán dung lượng và cấu hình cần thiết: Chọn loại EC2 instance (`t3.micro` hoặc `t3.small` để tối ưu chi phí), dung lượng RDS, quy tắc bảo mật.
   * Thiết lập **Amazon SES (Simple Email Service):** Xác thực domain/email gửi đi, đảm bảo tính năng gửi mã OTP thanh toán và vé điện tử hoạt động trơn tru trên môi trường thật.
3. **Lên kế hoạch Deploy:**
   * Lên danh sách các biến môi trường (Environment Variables) cần thiết cho Backend.
   * Đóng gói mã nguồn Frontend, cấu hình các đường dẫn API từ Localhost sang IP Public của EC2.

### Kết quả đạt được

* Hệ thống chạy ổn định, mượt mà trên môi trường máy cá nhân.
* Kế hoạch triển khai rõ ràng, các thông số AWS đã được tính toán kỹ lưỡng.
