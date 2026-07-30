---
title: "Week 7: AWS Deployment"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives

* Deploy core infrastructure components (Database, Storage) to the AWS Cloud environment.
* Host the Backend API on an EC2 virtual server and ensure full connectivity.

### Completed Tasks

1. **Initializing Amazon RDS (PostgreSQL):**
   * Created a PostgreSQL RDS instance.
   * Configured the Security Group to only allow connections from safe IP ranges.
   * Imported data from the SQL file (schema and sample data) into RDS.
2. **Setting up Amazon S3:**
   * Created an S3 bucket to host the Frontend source code (HTML/CSS/JS) and enabled the **Static Website Hosting** feature.
   * Configured the Bucket Policy to allow public read access.
3. **Deploying the Backend to Amazon EC2:**
   * Launched an EC2 instance running the Ubuntu operating system.
   * Connected via SSH to the EC2 instance, installed Node.js, PM2 (Process Manager), and Git.
   * Cloned the Backend source code from GitHub to EC2.
   * Updated the environment variables file (`.env`) to connect the Backend properly to the Amazon RDS endpoint.
   * Ran the Backend continuously using PM2 and opened port 3000 on the Security Group.

### Outcomes

* The database and Backend API are fully hosted on the cloud (AWS).
* The static Frontend is uploaded to S3 and can be accessed via the AWS endpoint URL.
