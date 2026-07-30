---
title: "Tuần 7: Deploy lên AWS (Giai đoạn 1)"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu Tuần 7

* Đưa các thành phần cơ sở hạ tầng cốt lõi (Database, Storage) lên môi trường Cloud AWS.
* Đưa Backend API lên máy chủ ảo EC2 và đảm bảo khả năng kết nối.

### Các công việc đã thực hiện

1. **Khởi tạo Amazon RDS (PostgreSQL):**
   * Tạo instance RDS PostgreSQL.
   * Cấu hình Security Group chỉ cho phép kết nối từ dải IP an toàn.
   * Import dữ liệu từ file SQL (schema và data mẫu) vào RDS.
2. **Thiết lập Amazon S3:**
   * Tạo bucket S3 để lưu trữ mã nguồn Frontend (HTML/CSS/JS) và cấu hình bật tính năng **Static Website Hosting**.
   * Cấu hình Bucket Policy để cho phép truy cập công khai (Public Read).
3. **Triển khai Backend lên Amazon EC2:**
   * Khởi tạo EC2 instance chạy hệ điều hành Ubuntu.
   * Kết nối SSH vào EC2, cài đặt Node.js, PM2 (Process Manager) và Git.
   * Clone source code Backend từ GitHub xuống EC2.
   * Cập nhật file biến môi trường (`.env`) để Backend kết nối đúng với endpoint của Amazon RDS.
   * Chạy Backend ngầm bằng PM2 và mở port 3000 trên Security Group.

### Kết quả đạt được

* Cơ sở dữ liệu và Backend API đã hoàn toàn nằm trên mây (AWS).
* Frontend tĩnh đã được upload lên S3 và có thể truy cập qua URL của AWS.
