+++
title = "5.5 CloudWatch"
date = 2021-08-11T14:26:07+07:00
weight = 5
chapter = false
pre = "<b>5.5. </b>"
+++

Trong phần này, chúng ta sẽ cấu hình **Amazon CloudWatch** để giám sát mức độ sử dụng CPU của máy chủ EC2 (Backend). Việc này giúp quản trị viên nhận được email cảnh báo (thông qua **Amazon SNS**) khi hệ thống bị quá tải.

### Bước 1: Tạo Chủ đề SNS (SNS Topic) để gửi email
1. Truy cập [AWS SNS Console](https://console.aws.amazon.com/sns/v3/home).
2. Chọn **Topics** ở menu bên trái và nhấn **Create topic**.
3. Chọn **Standard**, đặt tên là `EC2-CPU-Alert` và nhấn **Create topic**.
4. Trong trang chi tiết của Topic vừa tạo, nhấn **Create subscription**.
5. Chọn Protocol là **Email** và nhập địa chỉ email của bạn vào ô **Endpoint**. Nhấn **Create subscription**.

![Tạo SNS Topic](/images/5-Workshop/5.5-CloudWatch/5.5.1.png)

6. Kiểm tra hộp thư email của bạn, mở email từ AWS và nhấn **Confirm subscription**.

![Xác nhận Email](/images/5-Workshop/5.5-CloudWatch/5.5.2.png)

### Bước 2: Tạo Cảnh báo CloudWatch (CloudWatch Alarm)
1. Truy cập [AWS CloudWatch Console](https://console.aws.amazon.com/cloudwatch/home).
2. Chọn **All alarms** ở menu bên trái và nhấn **Create alarm**.
3. Nhấn **Select metric**. Di chuyển đến **EC2** > **Per-Instance Metrics**.
4. Tìm và tích chọn ô vuông bên cạnh Instance ID của con máy chủ Backend của bạn, với tên Metric là **CPUUtilization**. Nhấn **Select metric**.

![Chọn EC2 Metric](/images/5-Workshop/5.5-CloudWatch/5.5.3.png)

5. Ở phần **Conditions**, chọn **Greater/Equal (>=)** và nhập giá trị `80`. Nghĩa là cảnh báo sẽ kích hoạt khi CPU vượt quá 80%. Nhấn **Next**.

![Cấu hình Điều kiện](/images/5-Workshop/5.5-CloudWatch/5.5.4.png)

6. Ở phần **Notification**, chọn **In alarm**, và chọn SNS Topic `EC2-CPU-Alert` mà bạn vừa tạo ở Bước 1. Nhấn **Next**.

![Cấu hình Thông báo](/images/5-Workshop/5.5-CloudWatch/5.5.5.png)

7. Đặt tên cảnh báo là `High-CPU-Backend-Alert` và nhấn **Next**.
8. Cuộn xuống cuối trang và nhấn **Create alarm**.

### Bước 3: Kiểm tra trạng thái Alarm
Sau vài phút, trạng thái của Alarm sẽ chuyển sang **OK** (màu xanh lá) vì hiện tại CPU đang hoạt động bình thường dưới mức 80%.

![Hoàn thành CloudWatch Alarm](/images/5-Workshop/5.5-CloudWatch/5.5.6.png)
