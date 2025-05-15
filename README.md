**Internship Provider:**   _CODTECH_

**Intern:**               _Lingamsetty Poojitha_

**Intern ID:**             _CT04DM1229_

**Domain:**                _SQL_

**Duration:**              _4 Weeks_

**Title:**                 _Relational Data Handling with SQL JOINs_

**Mentor Name:**           _Neela Santhosh Kumar_

**Submission Type:**       _Practical Task + Documentation_

**📌 Objective**

The goal of this project is to demonstrate the use of various SQL JOIN operations to retrieve and combine data from related tables in a relational database. 

Through hands-on practice, we explore:

INNER JOIN

LEFT JOIN

RIGHT JOIN

FULL OUTER JOIN (via UNION, for MySQL)

We use a scenario involving Employees and Departments to show real-world data relationships and how JOINs extract meaningful information.

**🧱 Database and Table Design**

We create a database named JoinsDB, containing two tables:

Departments: stores department information.

Employees: stores employee information and their associated department.

**🏗️ Database Setup**

**1️⃣ Create Database and Use It**

-- Step 1: Create the database

CREATE DATABASE JoinsDB; 

-- Step 2: Use the database

USE JoinsDB;


**2️⃣ Create Tables**

-- Step 3: Create Departments table

CREATE TABLE Departments (
    DepartmentID INT PRIMARY KEY,
    DepartmentName VARCHAR(50)
);

-- Step 4: Create Employees table

CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    Name VARCHAR(50),
    DepartmentID INT
);

**3️⃣ Insert Sample Data**

-- Step 5: Insert data into Departments

INSERT INTO Departments (DepartmentID, DepartmentName) VALUES 

(10, 'HR'),

(20, 'IT'),

(40, 'Marketing');

-- Step 6: Insert data into Employees

INSERT INTO Employees (EmployeeID, Name, DepartmentID) VALUES

(1, 'Alice', 10),

(2, 'Bob', 20),

(3, 'Charlie', 30),  -- No matching department 

(4, 'David', NULL);  -- No department assigned


**📊 View Tables**
 
 -- Step 7: View Departments data
 
SELECT * FROM Departments;

-- Step 8: View Employees data

SELECT * FROM Employees;
      
**_🔍 SQL JOIN Queries_**

**✅ INNER JOIN**

Returns rows with matching DepartmentID in both tables.

-- Step 9: INNER JOIN

SELECT Employees.Name, Departments.DepartmentName

FROM Employees

INNER JOIN Departments

ON Employees.DepartmentID = Departments.DepartmentID;
  
**📌 Result:**

| Name  | DepartmentName |
| ----- | -------------- |
| Alice | HR             |
| Bob   | IT             |


**📥 LEFT JOIN**

Returns all rows from Employees, and matched rows from Departments.

-- Step 10: LEFT JOIN

SELECT Employees.Name, Departments.DepartmentName

FROM Employees

LEFT JOIN Departments

ON Employees.DepartmentID = Departments.DepartmentID;

**📌 Result:**

| Name    | DepartmentName |
| ------- | -------------- |
| Alice   | HR             |
| Bob     | IT             |
| Charlie | NULL           |
| David   | NULL           |

**📤 RIGHT JOIN**

Returns all rows from Departments, and matched rows from Employees.

-- Step 11: RIGHT JOIN

SELECT Employees.Name, Departments.DepartmentName

FROM Employees

RIGHT JOIN Departments

ON Employees.DepartmentID = Departments.DepartmentID;

**📌 Result:**

| Name  | DepartmentName |
| ----- | -------------- |
| Alice | HR             |
| Bob   | IT             |
| NULL  | Marketing      |

**🌐 FULL OUTER JOIN (Simulated with UNION)**

Combines LEFT JOIN and RIGHT JOIN to simulate a FULL OUTER JOIN.

-- Step 12: FULL OUTER JOIN (Simulated using UNION)

SELECT Employees.Name, Departments.DepartmentName

FROM Employees

LEFT JOIN Departments

ON Employees.DepartmentID = Departments.DepartmentID

UNION

SELECT Employees.Name, Departments.DepartmentName

FROM Employees

RIGHT JOIN Departments

ON Employees.DepartmentID = Departments.DepartmentID;

**📌 Result:**

| Name    | DepartmentName |
| ------- | -------------- |
| Alice   | HR             |
| Bob     | IT             |
| Charlie | NULL           |
| David   | NULL           |
| NULL    | Marketing      |

**📝 Summary of Joins**

| Join Type       | Description                                       | Nulls Possible From |
| --------------- | ------------------------------------------------- | ------------------- |
| INNER JOIN      | Matches in both tables only                       | ❌                   |
| LEFT JOIN       | All from left (`Employees`), matched from right   | Right Table         |
| RIGHT JOIN      | All from right (`Departments`), matched from left | Left Table          |
| FULL OUTER JOIN | All records from both tables                      | Both Tables         |

**🚀 How to Run**

1.Copy the SQL scripts into your database query tool (e.g., MySQL Workbench, DBeaver).

2.Run the table creation and insert script.

3.Run each JOIN query and observe the output.

4.Try modifying data to explore different join behaviors.

**📌 Notes**

 FULL OUTER JOIN is not natively supported in MySQL. The simulated version using UNION is used here.

 For NULL joins, remember that comparisons (=, !=) don’t match NULL, so always use IS NULL for filtering.



**📁  Structure**

joins-practice/

├── README.md               # Documentation file (this file)

├── joins_practice.sql      # Full SQL script with queries

├── screenshots/            #  Screenshots of results

└── LICENSE                 # License file

**📄 Deliverables**

✅ joins_practice.sql – SQL script containing all table creation, insert, and join queries

✅ README.md – GitHub-friendly documentation

✅ Screenshots (optional) – To visually show query outputs

✅ .docx or .pdf version of this documentation (on request)

**📜 License**

This project is part of the CODTECH Internship Program and is intended for educational purposes only.


**OUTPUTS SCREENSHOTS:** 

 _DEPARTMENTS TABLE_   :             ![Image](https://github.com/user-attachments/assets/945fee2d-c844-48c0-a72e-ae67fbe6aec4) 
                
_EMPLOYEE TABLE:_ ![Image](https://github.com/user-attachments/assets/aa90a500-06d9-4eb4-a0f2-30613a93b067)

_INNER JOIN_ : ![Image](https://github.com/user-attachments/assets/160e57dd-a422-472d-a43b-462acac84289)

_LEFT JOIN:_ ![Image](https://github.com/user-attachments/assets/7ac4d12e-4e06-4295-ac5e-ef0c5fc8f688)

_RIGHT JOIN :_![Image](https://github.com/user-attachments/assets/69488745-51c0-4100-b836-8397fa94f2b9)

_FULL JOIN :_ ![Image](https://github.com/user-attachments/assets/9f1c40fe-27cd-4c60-b2a6-38070265ed50)

               

