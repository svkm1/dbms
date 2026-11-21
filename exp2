-- PRACTICAL 2: Hospital database - DDL and DML
CREATE DATABASE IF NOT EXISTS Hospital;
USE Hospital;

DROP TABLE IF EXISTS Patient;

CREATE TABLE Patient (
    Patient_ID INT PRIMARY KEY,
    Patient_Name VARCHAR(50),
    Age INT,
    Gender VARCHAR(10),
    Disease VARCHAR(50),
    Fees DECIMAL(10,2)
);

INSERT INTO Patient VALUES
(1, 'Rahul', 22, 'Male', 'Fever', 500.00),
(2, 'Priya', 25, 'Female', 'Cold', 300.00),
(3, 'Amit', 30, 'Male', 'Diabetes', 1000.00),
(4, 'Sneha', 28, 'Female', 'Malaria', 800.00),
(5, 'Rohit', 35, 'Male', 'Typhoid', 1200.00);

-- Display all patients
SELECT * FROM Patient;

-- Update fees of a particular patient
UPDATE Patient
SET Fees = 1500.00
WHERE Patient_ID = 3;

-- Delete a particular patient
DELETE FROM Patient
WHERE Patient_ID = 4;

-- Add Contact column
ALTER TABLE Patient
ADD Contact VARCHAR(15);

-- Display final records
SELECT * FROM Patient;
