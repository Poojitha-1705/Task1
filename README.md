Internship Provider: CODTECH

Intern: Lingamsetty Poojitha

Intern ID:CT04DM1229

Domain :SQL

Duration:4 Weeks

Project Title: Relational Data Handling with SQL JOINs

Mentor Name: Neela Santhosh Kumar

Submission Type: Practical Task + Documentation

📌 Objective

The goal of this project is to demonstrate the use of various SQL JOIN operations to retrieve and combine data from related tables in a relational database. 

Through hands-on practice, we explore:

INNER JOIN

LEFT JOIN

RIGHT JOIN

FULL OUTER JOIN (via UNION, for MySQL)

We use a scenario involving Employees and Departments to show real-world data relationships and how JOINs extract meaningful information.

🧱 Database and Table Design

We create a database named JoinsDB, containing two tables:

Departments: stores department information.

Employees: stores employee information and their associated department.

🎯 Step 1: Create Database

sql

Copy

Edit

CREATE DATABASE JoinsDB;

USE JoinsDB;

🎯 Step 2: Create Tables

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

🎯 Step 3: Insert Sample Data

sql

Copy

Edit

-- Insert data into Departments

INSERT INTO Departments (DepartmentID, DepartmentName) VALUES

(10, 'HR'),

(20, 'IT'),

(40, 'Marketing');

-- Insert data into Employees

INSERT INTO Employees (EmployeeID, Name, DepartmentID) VALUES

(1, 'Alice', 10),

(2, 'Bob', 20),

(3, 'Charlie', 30),  -- DepartmentID 30 does not exist

(4, 'David', NULL);  -- David has no assigned department

🔎 Raw Data Overview

Employees Table

EmployeeID	Name	     DepartmentID

1	Alice	               10


2	Bob                    20

3	Charlie	               30 (No match)

4	David                	NULL

Departments Table

DepartmentID	DepartmentName

10	HR

20	IT

40	Marketing

🔄 JOIN Queries and Expected Results

🔹 INNER JOIN

sql

Copy

Edit

SELECT Employees.Name, Departments.DepartmentName

FROM Employees

INNER JOIN Departments

ON Employees.DepartmentID = Departments.DepartmentID;

Explanation:

Returns only rows where there is a match in both Employees and Departments.

Result:

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

Explanation:

Returns all records from Employees and matched records from Departments. If no match, NULL is returned.

Result:

Name	DepartmentName

Alice	HR

Bob	    IT
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

Explanation:

Returns all records from Departments and matched records from Employees. If no match, NULL is returned.

Result:

Name	DepartmentName
Alice	HR

Bob	    IT

NULL	Marketing

🔹 FULL OUTER JOIN (via UNION)

MySQL does not support FULL OUTER JOIN directly. We simulate it using UNION of LEFT JOIN and RIGHT JOIN.

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

Explanation:

Combines the results of both LEFT and RIGHT joins to ensure all rows from both tables are included.

Result:

Name	DepartmentName

Alice	HR

Bob  	IT

Charlie	NULL

David	NULL

NULL	Marketing

📚 Learnings and Key Takeaways

INNER JOIN: Retrieves only matching records.

LEFT JOIN: Retrieves all records from the left table, and matches from the right.

RIGHT JOIN: Retrieves all records from the right table, and matches from the left.

FULL OUTER JOIN: Ensures inclusion of all records from both tables.

📁 Project Structure

graphql

Copy

Edit
joins-practice/

├── README.md               # Documentation file (this file)

├── joins_practice.sql      # Full SQL script with queries

├── screenshots/            # (Optional) Screenshots of results

└── LICENSE                 # (Optional) License file

📄 Deliverables

✅ joins_practice.sql – SQL script containing all table creation, insert, and join queries

✅ README.md – GitHub-friendly documentation

✅ Screenshots (optional) – To visually show query outputs

✅ .docx or .pdf version of this documentation (on request)

📜 License

This project is part of the CODTECH Internship Program and is intended for educational purposes only.


OUTPUTS SCREENSHOTS:
 DEPARTMENTS TABLE   :             ![Image](https://github.com/user-attachments/assets/945fee2d-c844-48c0-a72e-ae67fbe6aec4) 
                
EMPLOYEE TABLE: ![Image](https://github.com/user-attachments/assets/aa90a500-06d9-4eb4-a0f2-30613a93b067)

INNER JOIN : ![Image](https://github.com/user-attachments/assets/160e57dd-a422-472d-a43b-462acac84289)

LEFT JOIN: ![Image](https://github.com/user-attachments/assets/7ac4d12e-4e06-4295-ac5e-ef0c5fc8f688)

RIGHT JOIN :![Image](https://github.com/user-attachments/assets/69488745-51c0-4100-b836-8397fa94f2b9)

FULL JOIN : ![Image](https://github.com/user-attachments/assets/9f1c40fe-27cd-4c60-b2a6-38070265ed50)

               

