# 🌩️ Web Applications Using Servlets and JSP

This project contains three independent web applications demonstrating the use of **Servlets**, **JSP**, and **JDBC** for handling user input, database connectivity, and dynamic web content generation.

Each part can be deployed separately on Apache Tomcat or run together in the same environment.

---

## 📁 Project Structure

Nimbus_WebApp/
│
├── PartA_UserLogin/
│ ├── web/
│ │ ├── login.html
│ │ └── WEB-INF/web.xml
│ └── src/com/nimbus/servlets/LoginServlet.java
│
├── PartB_EmployeeRecords/
│ ├── web/
│ │ ├── employees.html
│ │ └── WEB-INF/web.xml
│ └── src/com/nimbus/servlets/EmployeeServlet.java
│ └── database/create_employee_table.sql
│
├── PartC_AttendancePortal/
│ ├── web/
│ │ ├── attendance.jsp
│ │ ├── success.jsp
│ │ └── WEB-INF/web.xml
│ └── src/com/nimbus/servlets/AttendanceServlet.java
│ └── database/create_attendance_table.sql
│
└── README.md


---

## ⚙️ Requirements

- **Java JDK 11 or above**  
- **Apache Tomcat 9.0 or above**  
- **MySQL Server 8.0 or above**  
- **JDBC Driver:** `mysql-connector-j.jar` (place inside Tomcat’s `lib` folder)

---

## 🧩 Part A — User Login Using Servlet and HTML

**Objective:**  
Create a simple user login page handled by a Java Servlet.

**Features:**
- HTML form for username and password input  
- Servlet validates credentials (hardcoded)  
- Displays a personalized message  

**How to Run:**
1. Copy the `PartA_UserLogin` folder into Tomcat’s `webapps` directory.  
2. Start the Tomcat server.  
3. Open [http://localhost:8080/PartA_UserLogin/login.html](http://localhost:8080/PartA_UserLogin/login.html)  
4. Use credentials:  
   - Username: `admin`  
   - Password: `12345`

---

## 🧩 Part B — Display Employee Records (Servlet + JDBC)

**Objective:**  
Integrate Servlets with MySQL to fetch and display employee data.

**Database Table:**
```sql
CREATE TABLE Employee (
  EmpID INT PRIMARY KEY,
  Name VARCHAR(50),
  Salary DECIMAL(10,2)
);
```
---
Features:

Display all employee records

Search employees by ID

Results displayed dynamically in an HTML table
---
How to Run:

Execute create_employee_table.sql in MySQL.

Update database username and password in EmployeeServlet.java.

Copy the PartB_EmployeeRecords folder into Tomcat’s webapps directory.

Open http://localhost:8080/PartB_EmployeeRecords/employees.html

---
🧩 Part C — Student Attendance Portal (JSP + Servlet + JDBC)
Objective:
Develop a student attendance portal using JSP and Servlets for data input and processing.
---
Database Table:

```sql

CREATE TABLE Attendance (
  StudentID INT,
  AttendanceDate DATE,
  Status VARCHAR(10)
);
```
---
Features:

JSP form for attendance input

Servlet inserts records into the database

JSP confirmation page for success
---
How to Run:

Run create_attendance_table.sql in MySQL.

Update database username and password in AttendanceServlet.java.

Copy the PartC_AttendancePortal folder into Tomcat’s webapps directory.

Open http://localhost:8080/PartC_AttendancePortal/attendance.jsp

---
🧠 Concepts Demonstrated
Part	Concept	Technologies Used
A	Handling HTML form data using Servlets	HTML, Java Servlet
B	Database integration using JDBC	HTML, Servlet, MySQL
C	MVC architecture with JSP and Servlet	JSP, Servlet, MySQL

---
🚀 Running All Parts Together
Ensure MySQL is running and both Employee and Attendance tables are created.

Place all three folders (PartA_UserLogin, PartB_EmployeeRecords, PartC_AttendancePortal) inside Tomcat’s webapps directory.

Start Tomcat using bin/startup.bat (Windows) or bin/startup.sh (Linux/Mac).

Access from your browser:

http://localhost:8080/PartA_UserLogin/login.html

http://localhost:8080/PartB_EmployeeRecords/employees.html

http://localhost:8080/PartC_AttendancePortal/attendance.jsp

---
🧾 Summary
This project demonstrates the implementation of Servlets, JSP, and JDBC in Java web development — from simple login handling to database-driven apps and JSP integration.
