# Nimbus Submission: Spring and Hibernate Applications

## Overview

This repository contains three Java applications built using **Spring Framework** and **Hibernate ORM**.
Each part demonstrates a different concept — dependency injection, database CRUD operations, and transaction management.

### Parts Included

1. **Part A:** Dependency Injection using Spring (Java-based configuration)
2. **Part B:** CRUD operations on a `Student` entity using Hibernate ORM
3. **Part C:** Banking system with transaction management using Spring + Hibernate

---

## Directory Structure

```
NimbusSubmission/
│
├── PartA_SpringDI/
│   ├── src/main/java/com/example/di/
│   │   ├── config/AppConfig.java
│   │   ├── model/Course.java
│   │   ├── model/Student.java
│   │   └── MainApp.java
│
├── PartB_HibernateCRUD/
│   ├── src/main/java/com/example/hibernatecrud/
│   │   ├── model/Student.java
│   │   ├── dao/StudentDAO.java
│   │   └── MainApp.java
│   └── resources/hibernate.cfg.xml
│
├── PartC_SpringHibernateTransaction/
│   ├── src/main/java/com/example/banking/
│   │   ├── config/AppConfig.java
│   │   ├── model/Account.java
│   │   ├── model/Transaction.java
│   │   ├── dao/AccountDAO.java
│   │   ├── service/BankingService.java
│   │   └── MainApp.java
│   └── resources/hibernate.cfg.xml
│
└── README.md
```

---

## Prerequisites

* **Java 17** or higher
* **Maven** (or manually include Spring, Hibernate, and MySQL connector JARs)
* **MySQL** installed and running
* Database named `nimbusdb` created for Parts B and C

---

## Part A: Dependency Injection in Spring

### Description

* Demonstrates **Spring Dependency Injection** using Java-based configuration (`@Configuration` and `@Bean`).
* The `Student` class depends on the `Course` class.
* No XML configuration is used.

### How to Run

1. Navigate to `PartA_SpringDI/src/main/java`.
2. Compile:

```bash
javac -cp "path_to_spring_jars/*" com/example/di/*.java com/example/di/config/*.java com/example/di/model/*.java
```

3. Run:

```bash
java -cp ".:path_to_spring_jars/*" com.example.di.MainApp
```

**Expected Output:**

```
Student Name: John Doe
Enrolled in course: Artificial Intelligence
```

---

## Part B: Hibernate CRUD Operations

### Description

* Demonstrates **Create, Read, Update, Delete** using Hibernate ORM and MySQL.
* Hibernate configuration handled via `hibernate.cfg.xml`.
* Uses annotations for entity mapping.

### How to Run

1. Ensure MySQL service is active and `nimbusdb` exists.
2. Update `hibernate.cfg.xml` with your username and password.
3. Navigate to `PartB_HibernateCRUD/src/main/java`.
4. Compile:

```bash
javac -cp "path_to_hibernate_jars/*:path_to_mysql_connector/*" com/example/hibernatecrud/*.java com/example/hibernatecrud/model/*.java com/example/hibernatecrud/dao/*.java
```

5. Run:

```bash
java -cp ".:path_to_hibernate_jars/*:path_to_mysql_connector/*" com.example.hibernatecrud.MainApp
```

**Expected Output:**

```
Added sample students
Displayed all students
Updated a student record
Deleted a student record
Final student list displayed
```

---

## Part C: Spring + Hibernate Transaction Management

### Description

* Simulates a **banking system** demonstrating **transaction management** using Spring and Hibernate.
* `BankingService` ensures **atomic transactions** for money transfers.
* Uses `@Transactional` for declarative transaction handling.

### How to Run

1. Ensure MySQL is running and `nimbusdb` exists.
2. Update `hibernate.cfg.xml` with valid credentials.
3. Navigate to `PartC_SpringHibernateTransaction/src/main/java`.
4. Compile:

```bash
javac -cp "path_to_spring_jars/*:path_to_hibernate_jars/*:path_to_mysql_connector/*" com/example/banking/*.java com/example/banking/config/*.java com/example/banking/dao/*.java com/example/banking/model/*.java com/example/banking/service/*.java
```

5. Run:

```bash
java -cp ".:path_to_spring_jars/*:path_to_hibernate_jars/*:path_to_mysql_connector/*" com.example.banking.MainApp
```

**Expected Output:**

```
Created two accounts
Performed money transfer successfully
Updated balances displayed
If transfer fails, transaction is rolled back
```

---

## Notes

* All Spring configurations use **Java-based setup** (no XML).
* Hibernate sessions are managed manually where required.
* Add all dependencies in your classpath or manage them via **Maven**.
* Each part can run independently.

---

