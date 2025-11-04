# Online Student Management System

## Overview

This is a **Spring + Hibernate-based mini project** designed to manage students, courses, and fee payments.
It demonstrates the integration of **Spring Framework** and **Hibernate ORM** using layered architecture and Java-based configuration.

### Key Highlights

* **Dependency Injection (DI)** using Spring configuration classes
* **CRUD operations** implemented with Hibernate ORM
* **Transaction Management** for secure and atomic fee payments/refunds
* **Console-based Menu Interface** for user interaction

---

## Features

1. **Student Management**

   * Add, update, delete, and view student details
   * Assign students to specific courses

2. **Course Management**

   * Add, update, delete, and view available courses

3. **Fee Management**

   * Pay and refund student fees
   * Maintains atomic transactions with rollback on failure

4. **Interactive Console**

   * Menu-driven operations
   * Real-time confirmation and status messages

---

## Technologies Used

* **Java 11+**
* **Spring Framework** (Core, ORM, TX)
* **Hibernate ORM**
* **MySQL / H2 Database**
* **Maven** for dependency management
* **Log4j** for logging

---

## Folder Structure

```
OnlineStudentManagementSystem/
│
├── src/main/java/com/osm/
│   ├── app/
│   │   └── MainApp.java
│   ├── config/
│   │   └── AppConfig.java
│   ├── dao/
│   │   ├── StudentDAO.java
│   │   ├── StudentDAOImpl.java
│   │   ├── CourseDAO.java
│   │   ├── CourseDAOImpl.java
│   │   └── PaymentDAO.java
│   ├── model/
│   │   ├── Student.java
│   │   ├── Course.java
│   │   └── Payment.java
│   └── service/
│       ├── FeeService.java
│       └── FeeServiceImpl.java
│
├── src/main/resources/
│   ├── hibernate.cfg.xml
│   ├── log4j.properties
│   └── schema.sql
│
├── pom.xml
└── README.md
```

---

## Database Setup

1. Create a MySQL database:

```sql
CREATE DATABASE osm_db;
```

2. (Optional) Run the schema file to generate tables:

```sql
USE osm_db;
-- Run the script in src/main/resources/schema.sql
```

3. Update database credentials in `hibernate.cfg.xml`:

```xml
<property name="hibernate.connection.username">root</property>
<property name="hibernate.connection.password">your_password</property>
```

---

## Running the Project

1. **Clone or extract** the repository to your system.
2. **Open in IDE** (IntelliJ IDEA or Eclipse).
3. **Build using Maven:**

```bash
mvn clean install
```

4. **Run the Application:**

   * From IDE → Run `MainApp.java`
   * Or from terminal:

   ```bash
   java -jar target/OnlineStudentManagementSystem-1.0-SNAPSHOT.jar
   ```

5. **Use the Console Menu:**

```
=== Online Student Management System ===
1. Add Student
2. View Student by ID
3. View All Students
4. Pay Fee
5. Refund Fee
0. Exit
Enter your choice:
```

---

## Notes

* Transactions ensure **atomicity** — payments and refunds rollback if any issue occurs.
* Hibernate auto-generates tables when `hbm2ddl.auto=update`.
* For quick testing, replace MySQL configuration with **H2 Database** in memory mode.

---
