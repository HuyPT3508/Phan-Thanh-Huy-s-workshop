---
title: "Week 5: Advanced Features (Real-time)"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives

* Implement advanced features requiring high data synchronization.
* Solve the Race Condition problem when multiple users try to book the same seat.
* Apply WebSockets technology to update the UI in real-time.

### Completed Tasks

1. **Solving the Seat Locking Problem:**
   * Integrated **Amazon DynamoDB** (simulated locally via NoSQL) to store temporary seat locking states with a Time-To-Live (TTL) of 5 minutes.
   * If a user does not complete the payment within 5 minutes, the seat is automatically released for others to choose.
   * Ensured data consistency (ACID) when recording the final ticket into PostgreSQL.
2. **Integrating Socket.IO (Real-time):**
   * Installed the Socket.IO library on the Node.js Backend.
   * Built the connection flow: When Customer A clicks on a seat, a signal is sent to the Server, and the Server immediately broadcasts it to Customers B, C, and D viewing the same showtime, turning the seat color to "Locked" (Gray).
3. **Developing Checkout & QR Ticket Flow:**
   * Integrated the encoding of order information into an e-ticket QR code.
   * Finalized the ticket history section in the Customer's profile page.

### Outcomes

* Completely resolved the issue of 2 people booking the same seat.
* The seat selection interface now responds instantly (in real-time) to the actions of other users.
