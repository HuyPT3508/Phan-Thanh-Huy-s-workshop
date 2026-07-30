---
title: "Tuần 8: Hoàn thiện hệ thống & Báo cáo"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu Tuần 8

* Đưa các dịch vụ nâng cao (DynamoDB, SES) lên môi trường Production.
* Thực hiện kiểm thử toàn trình (End-to-End) trên hệ thống AWS thực tế.
* Hoàn thiện tài liệu, quay video demo và đóng gói dự án để báo cáo.

### Các công việc đã thực hiện

1. **Deploy Amazon DynamoDB & SES:**
   * Thay thế cơ sở dữ liệu khóa ghế NoSQL ở Local bằng bảng thật trên **Amazon DynamoDB**. Cấu hình IAM Role cho EC2 để có quyền ghi dữ liệu vào DynamoDB an toàn mà không cần hardcode Access Key.
   * Áp dụng **Amazon SES** trên Production. Đưa địa chỉ email của hệ thống ra khỏi chế độ Sandbox (hoặc verify các email test) để có thể gửi mã OTP xác thực và gửi email hoàn tiền.
2. **Kiểm thử E2E (End-to-End Testing) & Sửa lỗi:**
   * Cập nhật các đường dẫn API trong source code Frontend (S3) để trỏ đến IP Public của EC2.
   * Thử nghiệm luồng mua vé từ đầu đến cuối: Truy cập web S3 -> Gọi API EC2 -> Đăng ký nhận OTP từ SES -> Lưu dữ liệu tạm vào DynamoDB -> Thanh toán thành công ghi vào RDS.
   * Phát hiện và khắc phục một số lỗi liên quan đến đường dẫn ảnh và CORS (Cross-Origin Resource Sharing) giữa S3 và EC2.
3. **Tổng kết & Báo cáo:**
   * Tối ưu hóa chi phí (Tắt/xóa các tài nguyên AWS không dùng đến).
   * Cập nhật giao diện Admin (Thêm Logo, làm sạch giao diện).
   * Viết tài liệu báo cáo kỹ thuật và quay video Demo toàn bộ quy trình chạy thực tế của hệ thống.

### Kết quả đạt được

* Hệ thống **HCMUT Cinema** hoạt động hoàn hảo 100% trên môi trường AWS, chịu tải tốt, xử lý đồng bộ thời gian thực mượt mà.
* Khóa huấn luyện kết thúc thành công với một đồ án Cloud-Native hoàn chỉnh.
