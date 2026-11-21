-- PRACTICAL 4: Display employee records using a cursor
CREATE DATABASE IF NOT EXISTS Company;
USE Company;

DROP PROCEDURE IF EXISTS DisplayEmployees;
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

DELIMITER //

CREATE PROCEDURE DisplayEmployees()
BEGIN
    DECLARE v_done INT DEFAULT 0;
    DECLARE v_id INT;
    DECLARE v_name VARCHAR(50);
    DECLARE v_department VARCHAR(30);
    DECLARE v_salary DECIMAL(10,2);

    DECLARE employee_cursor CURSOR FOR
        SELECT Employee_ID, Employee_Name, Department, Salary
        FROM Employee;

    DECLARE CONTINUE HANDLER FOR NOT FOUND
        SET v_done = 1;

    OPEN employee_cursor;

    read_loop: LOOP
        FETCH employee_cursor
        INTO v_id, v_name, v_department, v_salary;

        IF v_done = 1 THEN
            LEAVE read_loop;
        END IF;

        SELECT
            v_id AS Employee_ID,
            v_name AS Employee_Name,
            v_department AS Department,
            v_salary AS Salary;
    END LOOP;

    CLOSE employee_cursor;
END //

DELIMITER ;

CALL DisplayEmployees();
