# 🎓 Campus Event Booking System

> A role-based web application designed to digitize and streamline the event booking and approval process on a college campus.

## 📖 Introduction
This project manages event bookings on a college campus by digitizing the entire process—from a student's initial request to the final approval from the Principal—through a clear, multi-level approval workflow. 

The system is designed to provide a secure and efficient experience for different user roles, ensuring that each user only sees the information and actions relevant to their position and authority level.

---

## ✨ Core Features

* **🔐 User Registration & Secure Login:** * Users can register for an account with a specific role (e.g., Student, Staff Advisor, HOD). 
    * Passwords are securely hashed, and the login system is robustly managed by **Spring Security**.
* **🎛️ Role-Based Dashboards:** * After logging in, users are automatically redirected to a dashboard tailored to their role.
    * **Student Dashboard:** Students can submit new event booking requests and view the live status (Pending, Approved, Rejected) of their past submissions.
    * **Approver Dashboards:** Each level of approver has a dedicated dashboard showing only the booking requests currently awaiting their specific approval.
* **✅ Multi-Level Approval Workflow:** * A booking request submitted by a student must be approved sequentially through the chain of command: **Staff Advisor ➡️ HOD ➡️ Dean ➡️ Principal**.
    * A rejection at any level stops the process immediately, while an approval moves the request to the next authority level.
* **🎨 Dynamic Frontend:** * The user interface is built with Thymeleaf and styled with a modern dark theme, providing a clean, responsive, and user-friendly experience.

---

## 🛠️ Technologies Used

### Backend
* **Java 25**
* **Spring Boot 3:** Core framework for the application.
* **Spring Security:** Handles authentication (login) and authorization (role-based access).
* **Spring Data JPA (Hibernate):** Facilitates database communication and maps Java objects to database tables.

### Database
* **MySQL:** Relational database management system.

### Frontend
* **Thymeleaf:** Modern server-side Java template engine for creating dynamic HTML pages.
* **HTML5 & CSS3:** For structuring and styling the web pages.

### Build Tool
* **Maven:** Manages project dependencies and application builds.

---

## 🚀 How to Run the Application

Follow these steps to get the application running on your local machine:

### 1. Database Setup
Ensure you have a MySQL server running locally. Create a new, empty database named `campus_booking`:
```sql
CREATE DATABASE campus_booking;
