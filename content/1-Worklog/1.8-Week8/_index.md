---
title: "Week 8: System Finalization & Reporting"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives

* Push advanced services (DynamoDB, SES) to the Production environment.
* Conduct End-to-End (E2E) testing on the actual AWS system.
* Complete documentation, record a demo video, and package the project for the final report.

### Completed Tasks

1. **Deploying Amazon DynamoDB & SES:**
   * Replaced the local NoSQL seat locking database with a real table on **Amazon DynamoDB**. Configured the IAM Role for EC2 to securely write data to DynamoDB without hardcoding Access Keys.
   * Applied **Amazon SES** on Production. Moved the system's email address out of Sandbox mode (or verified test emails) to enable sending authentication OTPs and refund emails.
2. **E2E Testing & Bug Fixing:**
   * Updated the API endpoints in the Frontend source code (S3) to point to the Public IP of the EC2 instance.
   * Tested the end-to-end booking flow: Access S3 web -> Call EC2 API -> Register to receive OTP from SES -> Store temporary data in DynamoDB -> Successful payment written to RDS.
   * Detected and fixed some issues related to image paths and CORS (Cross-Origin Resource Sharing) between S3 and EC2.
3. **Summary & Reporting:**
   * Optimized costs (Turned off/deleted unused AWS resources).
   * Updated the Admin interface (Added Logo, cleaned up UI).
   * Wrote technical report documentation and recorded a Demo video of the entire real-world process of the system.

### Outcomes

* The **HCMUT Cinema** system works 100% perfectly on the AWS environment, handling load well and smoothly processing real-time synchronization.
* The bootcamp successfully concluded with a fully functional Cloud-Native project.
