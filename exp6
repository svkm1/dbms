-- PRACTICAL 6: INNER, LEFT, RIGHT, CROSS and FULL OUTER JOIN
CREATE DATABASE IF NOT EXISTS Company;
USE Company;

DROP TABLE IF EXISTS Employee;
DROP TABLE IF EXISTS Department;

CREATE TABLE Department (
    Department_ID INT PRIMARY KEY,
    Department_Name VARCHAR(50)
);

CREATE TABLE Employee (
    Employee_ID INT PRIMARY KEY,
    Employee_Name VARCHAR(50),
    Department_ID INT,
    Salary DECIMAL(10,2)
);

INSERT INTO Department VALUES
(101, 'IT'),
(102, 'HR'),
(103, 'Finance'),
(104, 'Sales');

INSERT INTO Employee VALUES
(1, 'Rahul', 101, 50000.00),
(2, 'Amit', 102, 40000.00),
(3, 'Priya', 103, 60000.00),
(4, 'Sneha', 101, 45000.00),
(5, 'Rohit', NULL, 35000.00);

-- 1. INNER JOIN: only matching records
SELECT E.Employee_Name, D.Department_Name
FROM Employee AS E
INNER JOIN Department AS D
    ON E.Department_ID = D.Department_ID;

-- 2. LEFT JOIN: all employees and matching departments
SELECT E.Employee_Name, D.Department_Name
FROM Employee AS E
LEFT JOIN Department AS D
    ON E.Department_ID = D.Department_ID;

-- 3. RIGHT JOIN: all departments and matching employees
SELECT E.Employee_Name, D.Department_Name
FROM Employee AS E
RIGHT JOIN Department AS D
    ON E.Department_ID = D.Department_ID;

-- 4. CROSS JOIN: Cartesian product (5 x 4 = 20 rows)
SELECT E.Employee_Name, D.Department_Name
FROM Employee AS E
CROSS JOIN Department AS D;

-- 5. FULL OUTER JOIN equivalent in MySQL using UNION
SELECT E.Employee_Name, D.Department_Name
FROM Employee AS E
LEFT JOIN Department AS D
    ON E.Department_ID = D.Department_ID

UNION

SELECT E.Employee_Name, D.Department_Name
FROM Employee AS E
RIGHT JOIN Department AS D
    ON E.Department_ID = D.Department_ID;
