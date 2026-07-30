+++
title = "5.5 CloudWatch"
date = 2021-08-11T14:26:07+07:00
weight = 5
chapter = false
pre = "<b>5.5. </b>"
+++

In this section, we will configure **Amazon CloudWatch** to monitor the CPU utilization of the EC2 instance (Backend). This ensures the administrator receives an email alert (via **Amazon SNS**) when the system becomes overloaded.

### Step 1: Create an SNS Topic for email alerts
1. Go to the [AWS SNS Console](https://console.aws.amazon.com/sns/v3/home).
2. Select **Topics** on the left menu and click **Create topic**.
3. Choose **Standard**, name it `EC2-CPU-Alert`, and click **Create topic**.
4. In the details page of the newly created Topic, click **Create subscription**.
5. Choose **Email** for Protocol and enter your email address in the **Endpoint** field. Click **Create subscription**.

![Create SNS Topic](/images/5-Workshop/5.5-CloudWatch/5.5.1.png)

6. Check your email inbox, open the email from AWS, and click **Confirm subscription**.

![Confirm Email](/images/5-Workshop/5.5-CloudWatch/5.5.2.png)

### Step 2: Create a CloudWatch Alarm
1. Go to the [AWS CloudWatch Console](https://console.aws.amazon.com/cloudwatch/home).
2. Select **All alarms** on the left menu and click **Create alarm**.
3. Click **Select metric**. Navigate to **EC2** > **Per-Instance Metrics**.
4. Find and check the box next to your Backend EC2 Instance ID, with the Metric name **CPUUtilization**. Click **Select metric**.

![Select EC2 Metric](/images/5-Workshop/5.5-CloudWatch/5.5.3.png)

5. Under **Conditions**, choose **Greater/Equal (>=)** and enter `80`. This means the alarm triggers when CPU exceeds 80%. Click **Next**.

![Configure Conditions](/images/5-Workshop/5.5-CloudWatch/5.5.4.png)

6. Under **Notification**, select **In alarm**, and choose the `EC2-CPU-Alert` SNS Topic created in Step 1. Click **Next**.

![Configure Notification](/images/5-Workshop/5.5-CloudWatch/5.5.5.png)

7. Name the alarm `High-CPU-Backend-Alert` and click **Next**.
8. Scroll to the bottom and click **Create alarm**.

### Step 3: Check Alarm Status
After a few minutes, the Alarm status will change to **OK** (green) because the current CPU usage is normally below 80%.

![Complete CloudWatch Alarm](/images/5-Workshop/5.5-CloudWatch/5.5.6.png)
