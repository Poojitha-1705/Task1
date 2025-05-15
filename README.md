# Task1
# 📊 SQL JOINs Practice – Internship Project

**Organization:** CODTECH  
**Intern:** *[Your Name]*  
**Project:** SQL Joins Practice  
**Certificate:** Will be issued upon internship completion

---

## 📌 Objective

This project demonstrates the use of SQL `JOIN` operations to meaningfully combine data from two related tables: `Employees` and `Departments`. The following joins are covered:

- INNER JOIN  
- LEFT JOIN  
- RIGHT JOIN  
- FULL OUTER JOIN (using UNION)

---

## 🛠️ Setup Instructions

### 1. Create the Database

```sql
CREATE DATABASE JoinsDB;
USE JoinsDB;
2. Create Tables
Departments Table
sql
Copy
Edit
CREATE TABLE Departments (
    DepartmentID INT PRIMARY KEY,
    DepartmentName VARCHAR(50)
);
Employees Table
sql
Copy
Edit
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    Name VARCHAR(50),
    DepartmentID INT
);
3. Insert Sample Data
sql
Copy
Edit
-- Insert into Departments
INSERT INTO Departments (DepartmentID, DepartmentName) VALUES
(10, 'HR'),
(20, 'IT'),
(40, 'Marketing');

-- Insert into Employees
INSERT INTO Employees (EmployeeID, Name, DepartmentID) VALUES
(1, 'Alice', 10),
(2, 'Bob', 20),
(3, 'Charlie', 30),
(4, 'David', NULL);
🔄 JOIN Operations
🔹 INNER JOIN
sql
Copy
Edit
SELECT Employees.Name, Departments.DepartmentName
FROM Employees
INNER JOIN Departments
ON Employees.DepartmentID = Departments.DepartmentID;
Expected Output:

Name	DepartmentName
Alice	HR
Bob	IT

🔹 LEFT JOIN
sql
Copy
Edit
SELECT Employees.Name, Departments.DepartmentName
FROM Employees
LEFT JOIN Departments
ON Employees.DepartmentID = Departments.DepartmentID;
Expected Output:

Name	DepartmentName
Alice	HR
Bob	IT
Charlie	NULL
David	NULL

🔹 RIGHT JOIN
sql
Copy
Edit
SELECT Employees.Name, Departments.DepartmentName
FROM Employees
RIGHT JOIN Departments
ON Employees.DepartmentID = Departments.DepartmentID;
Expected Output:

Name	DepartmentName
Alice	HR
Bob	IT
NULL	Marketing

🔹 FULL OUTER JOIN (Simulated using UNION)
sql
Copy
Edit
SELECT Employees.Name, Departments.DepartmentName
FROM Employees
LEFT JOIN Departments
ON Employees.DepartmentID = Departments.DepartmentID

UNION

SELECT Employees.Name, Departments.DepartmentName
FROM Employees
RIGHT JOIN Departments
ON Employees.DepartmentID = Departments.DepartmentID;
Expected Output:

Name	DepartmentName
Alice	HR
Bob	IT
Charlie	NULL
David	NULL
NULL	Marketing

✅ Summary
This project illustrates how SQL JOINs are used to manage relationships between tables and extract meaningful insights. It covers how to handle matched and unmatched records in various scenarios using JOIN types.

📁 Files
joins_practice.sql – Full SQL script

README.md – Project documentation

(Optional) screenshots/ – Output screenshots

📜 License
This project is for educational purposes under the CODTECH Internship Program.
