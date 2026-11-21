-- PRACTICAL 8: Triggers for account INSERT and UPDATE logging
CREATE DATABASE IF NOT EXISTS Bank;
USE Bank;

DROP TRIGGER IF EXISTS after_account_insert;
DROP TRIGGER IF EXISTS after_account_update;
DROP TABLE IF EXISTS Account_Log;
DROP TABLE IF EXISTS Account;

CREATE TABLE Account (
    Account_ID INT PRIMARY KEY,
    Account_Name VARCHAR(50),
    Balance DECIMAL(10,2)
);

CREATE TABLE Account_Log (
    Log_ID INT AUTO_INCREMENT PRIMARY KEY,
    Account_ID INT,
    Account_Name VARCHAR(50),
    Balance DECIMAL(10,2),
    Action_Type VARCHAR(20),
    Action_Date TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

DELIMITER //

CREATE TRIGGER after_account_insert
AFTER INSERT ON Account
FOR EACH ROW
BEGIN
    INSERT INTO Account_Log
        (Account_ID, Account_Name, Balance, Action_Type)
    VALUES
        (NEW.Account_ID, NEW.Account_Name, NEW.Balance, 'INSERT');
END //

CREATE TRIGGER after_account_update
AFTER UPDATE ON Account
FOR EACH ROW
BEGIN
    INSERT INTO Account_Log
        (Account_ID, Account_Name, Balance, Action_Type)
    VALUES
        (NEW.Account_ID, NEW.Account_Name, NEW.Balance, 'UPDATE');
END //

DELIMITER ;

INSERT INTO Account VALUES
(101, 'Rahul', 10000.00),
(102, 'Amit', 15000.00),
(103, 'Priya', 20000.00),
(104, 'Sneha', 12000.00),
(105, 'Rohit', 8000.00);

UPDATE Account
SET Balance = 15000.00
WHERE Account_ID = 101;

SELECT * FROM Account;
SELECT * FROM Account_Log;
