-- PRACTICAL 7: MySQL built-in and aggregate functions
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

-- 1. Total salary
SELECT SUM(Salary) AS Total_Salary
FROM Employee;

-- 2. Average salary
SELECT AVG(Salary) AS Average_Salary
FROM Employee;

-- 3. Employee names in uppercase
SELECT UPPER(Employee_Name) AS Upper_Name
FROM Employee;

-- 4. Minimum salary
SELECT MIN(Salary) AS Minimum_Salary
FROM Employee;

-- 5. Department-wise employee count
SELECT Department, COUNT(*) AS Total_Employees
FROM Employee
GROUP BY Department;

-- Additional functions requested in the practical
SELECT COUNT(*) AS Employee_Count FROM Employee;
SELECT MAX(Salary) AS Maximum_Salary FROM Employee;
SELECT LOWER(Employee_Name) AS Lower_Name FROM Employee;
SELECT ROUND(AVG(Salary), 2) AS Rounded_Average_Salary FROM Employee;
