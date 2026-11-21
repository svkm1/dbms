-- PRACTICAL 5: Nested queries / subqueries
CREATE DATABASE IF NOT EXISTS Company;
USE Company;

DROP TABLE IF EXISTS Employee;

CREATE TABLE Employee (
    Employee_ID INT PRIMARY KEY,
    Employee_Name VARCHAR(50),
    Department VARCHAR(30),
    Salary DECIMAL(10,2)
);

INSERT INTO Employee VALUES
(1, 'Rahul', 'IT', 50000.00),
(2, 'Amit', 'HR', 40000.00),
(3, 'Priya', 'IT', 60000.00),
(4, 'Sneha', 'Finance', 45000.00),
(5, 'Rohit', 'Sales', 35000.00);

-- 1. Employees having salary greater than average salary
SELECT *
FROM Employee
WHERE Salary > (SELECT AVG(Salary) FROM Employee);

-- 2. Employee(s) having maximum salary
SELECT *
FROM Employee
WHERE Salary = (SELECT MAX(Salary) FROM Employee);

-- 3. Employees working in the IT department (using a subquery)
SELECT *
FROM Employee
WHERE Department = (
    SELECT Department
    FROM Employee
    WHERE Employee_Name = 'Rahul'
);

-- 4. Employees having salary greater than Rahul
SELECT *
FROM Employee
WHERE Salary > (
    SELECT Salary
    FROM Employee
    WHERE Employee_Name = 'Rahul'
);

-- 5. Employees working in the same department as Rahul
SELECT *
FROM Employee
WHERE Department = (
    SELECT Department
    FROM Employee
    WHERE Employee_Name = 'Rahul'
);
