---
title: "Week 4: Setup & Core Features"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives

* Initialize the project and set up the Local development environment.
* Refactor the legacy source code, clean up the codebase, and transition to a standard structure.
* Build basic core features: Login, Viewing the movie list.

### Completed Tasks

1. **Local Environment Setup:**
   * Installed Node.js and Express for the Backend.
   * Installed PostgreSQL on personal machines to simulate the Database before migrating to RDS.
   * Built a basic Frontend using vanilla HTML/CSS/JS without heavy frameworks for easier optimization when deploying to S3.
2. **Refactoring Legacy Code:**
   * Removed redundant code from the original sample project.
   * Rewrote database query APIs using parameterized queries to prevent SQL Injection.
   * Restructured the project directory: separated `routes`, `controllers`, and `config`.
3. **Developing Core Features:**
   * Built the API to fetch the list of currently showing movies.
   * Built a basic Admin page to add/delete/edit movies.

### Outcomes

* The development environment is fully ready.
* The Frontend can connect to the Local Backend and successfully call APIs.
* Ready to develop more complex features in the coming week.
