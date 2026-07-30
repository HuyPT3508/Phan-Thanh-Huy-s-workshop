---
title: "Tuần 3: Chốt dự án & Kiến trúc"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu Tuần 3

* Quyết định chọn chủ đề chính thức cho đồ án.
* Thiết kế kiến trúc tổng thể cho hệ thống theo tiêu chuẩn Cloud-Native.
* Phân công nhiệm vụ cụ thể cho từng thành viên trong nhóm.

### Các công việc đã thực hiện

1. **Chốt dự án:**
   * Nhóm quyết định chọn **Hệ thống đặt vé rạp chiếu phim (HCMUT Cinema)** làm đồ án cuối kỳ.
   * Đây là một bài toán thực tế, đòi hỏi phải xử lý các vấn đề như: đồng bộ dữ liệu thời gian thực (tránh trùng ghế), gửi email xác nhận tự động, và yêu cầu tính khả dụng cao.
2. **Thiết kế Kiến trúc Hệ thống (AWS Architecture):**
   * **Compute:** Sử dụng **Amazon EC2** để host Backend API (Node.js/Express).
   * **Storage:** Sử dụng **Amazon S3** để lưu trữ Frontend dạng tĩnh (HTML/CSS/JS) và tài nguyên hình ảnh.
   * **Database:** 
     * **Amazon RDS (PostgreSQL):** Lưu trữ dữ liệu quan hệ (Người dùng, Phim, Suất chiếu, Vé).
     * **Amazon DynamoDB:** Quản lý trạng thái khóa ghế (Seat Locking) tạm thời tốc độ cao.
   * **Networking & Security:** Thiết lập VPC, Security Groups đảm bảo Backend và Database được bảo mật.
   * **Messaging:** Tích hợp **Amazon SES** để gửi OTP và vé điện tử qua Email.
3. **Phân công công việc:**
   * Chia nhỏ các task trên Trello.
   * Phân chia vai trò: Frontend Developer, Backend Developer, và Cloud/DevOps Engineer.

### Kết quả đạt được

* Có bản vẽ kiến trúc hệ thống rõ ràng.
* Sẵn sàng bước vào giai đoạn Code (Tuần 4).
