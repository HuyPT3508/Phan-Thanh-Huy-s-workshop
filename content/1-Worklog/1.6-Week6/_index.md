---
title: "Week 6: Local Testing & Pre-Deployment"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives

* Perform End-to-End testing on the Local environment to detect bugs.
* Finalize and fix unstable feature flows (Fix bugs).
* Draft a detailed Deployment Plan for the Cloud environment (AWS).

### Completed Tasks

1. **Testing and Bug Fixing:**
   * Fixed a bug where the Frontend did not send the correct ticket price (GiaVe) to the Backend when customers purchased VIP or IMAX seats.
   * Improved the Admin UI/UX, added the university logo, and optimized error messages for users.
   * Handled the refund flow: Simulated a scenario where the Admin deletes a movie that already has booked tickets, and wrote a trigger to automatically send notification emails.
2. **Preparing AWS Infrastructure:**
   * Calculated required capacities and configurations: Selected EC2 instance types (`t3.micro` or `t3.small` to optimize costs), RDS storage, and security rules.
   * Configured **Amazon SES (Simple Email Service):** Verified the sender domain/email to ensure the payment OTP and e-ticket features work smoothly in the production environment.
3. **Deployment Planning:**
   * Created a list of required Environment Variables for the Backend.
   * Bundled the Frontend source code, and reconfigured the API base URLs from Localhost to the Public IP of the EC2 instance.

### Outcomes

* The system runs stably and smoothly on local machines.
* A clear deployment plan is ready, with all AWS parameters carefully calculated.
