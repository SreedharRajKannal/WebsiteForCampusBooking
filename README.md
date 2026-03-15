# 🎓 Campus Event Booking System

![Java](https://img.shields.io/badge/Java-25-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-%23005C0F.svg?style=for-the-badge&logo=Thymeleaf&logoColor=white)

> A robust, role-based web application designed to digitize the multi-level approval workflow for event bookings on a college campus.

## 📖 Introduction
This project automates the manual paperwork involved in campus facility management. It tracks a booking request from the initial student submission through a sequential approval chain (Staff Advisor ➡️ HOD ➡️ Dean ➡️ Principal), ensuring transparency and accountability at every stage.

---

## ✨ Key Features

* **🔐 Secure Auth & RBAC:** Managed by **Spring Security** with **BCrypt** password hashing. Roles include Student, Staff Advisor, HOD, Dean, and Principal.
* **📜 Approved History Log:** A dedicated audit trail for approvers. Once a booking is finalized, a "snapshot" of the data is archived, allowing Staff and HODs to view their previously approved requests even if the original data changes.
* **✅ Multi-Level Sequential Workflow:** Logic-driven status updates. A rejection at any level terminates the request, while approval promotes it to the next authority.
* **🎛️ Intelligent Dashboards:** Real-time data filtering. Users only see tasks relevant to their specific role and approval stage.
* **🎨 Modern Dark UI:** A fully responsive frontend built with **Thymeleaf** and **CSS3**, optimized for both desktop and mobile viewing.

---

## 🛠️ Technologies Used

| Layer | Technology |
| :--- | :--- |
| **Backend** | Java 25, Spring Boot 3.4+, Spring Security |
| **Persistence** | Spring Data JPA, Hibernate, MySQL 8.0 |
| **Frontend** | Thymeleaf, HTML5, CSS3 (Modern Dark Theme) |
| **Build Tool** | Maven |

---

## 📂 Database Architecture

To ensure high data integrity and an audit trail, the system utilizes the following core entities:

* **`person`**: Stores user credentials, BCrypt hashes, and roles.
* **`bookings`**: Tracks active booking requests through the approval lifecycle.
* **`approved_booking_history`**: An archive table that stores redundant snapshots of finalized bookings for historical reporting.

---
## 🚀 Getting Started

### 1. Database Setup
Ensure MySQL is running. Create the database and the history table:
```sql
CREATE DATABASE campus_booking;

-- The application will auto-generate most tables, 
-- but ensure your 'person' table has a SuperUser:
INSERT INTO person (dtype, name, password, role) 
VALUES ('SuperUser', 'root', '$2a$10$8K1p/a0jlpx8pnyC2vG9u.Ym8yW9Z9yZ9yZ9yZ9yZ9yZ9yZ9yZ9y', 'ROLE_SUPER_USER');

Follow these steps to get the application running on your local machine:

### 1. Database Setup
Ensure you have a MySQL server running locally. Create a new, empty database named `campus_booking`:

```sql
CREATE DATABASE campus_booking;
```
### 2. Configuration
Open the src/main/resources/application.properties file and update your database credentials to match your `local MySQL setup`:

```properties
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password
```
### 3. Run the Application
You can run the application using your preferred `IDE` (by executing the main method in WebApplication.java), or by using the `terminal`.

To run via `terminal`, navigate to the project's root directory and execute:

```bash
./mvnw spring-boot:run
```
### 4. Access the Web App
Once the application has started successfully, open your web browser and navigate to:

```text
http://localhost:8080
```
