---
title: "Week 3: Finalizing Project & Architecture"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives

* Officially decide on the main topic for the project.
* Design the overall system architecture following Cloud-Native standards.
* Assign specific tasks to each team member.

### Completed Tasks

1. **Finalizing the Project:**
   * The team decided to select the **Cinema Ticket Booking System (HCMUT Cinema)** as the final project.
   * This is a practical problem that requires handling issues such as real-time data synchronization (to prevent double-booking seats), automated confirmation emails, and high availability requirements.
2. **System Architecture Design (AWS Architecture):**
   * **Compute:** Use **Amazon EC2** to host the Backend API (Node.js/Express).
   * **Storage:** Use **Amazon S3** to host the static Frontend (HTML/CSS/JS) and image resources.
   * **Database:** 
     * **Amazon RDS (PostgreSQL):** Store relational data (Users, Movies, Showtimes, Tickets).
     * **Amazon DynamoDB:** Manage high-speed temporary Seat Locking states.
   * **Networking & Security:** Set up VPC and Security Groups to ensure the Backend and Database are secure.
   * **Messaging:** Integrate **Amazon SES** to send OTPs and e-tickets via Email.
3. **Task Assignment:**
   * Broke down tasks on Trello.
   * Divided roles: Frontend Developer, Backend Developer, and Cloud/DevOps Engineer.

### Outcomes

* Produced a clear system architecture diagram.
* Ready to enter the Coding phase (Week 4).
