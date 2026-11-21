-- PRACTICAL 3: Bank withdrawal procedure with exception handling
CREATE DATABASE IF NOT EXISTS Bank;
USE Bank;

DROP PROCEDURE IF EXISTS WithdrawMoney;
DROP TABLE IF EXISTS Account;

CREATE TABLE Account (
    Account_No INT PRIMARY KEY,
    Account_Name VARCHAR(50),
    Balance DECIMAL(10,2)
);

INSERT INTO Account VALUES
(101, 'Rahul', 10000.00),
(102, 'Amit', 15000.00),
(103, 'Priya', 20000.00),
(104, 'Sneha', 12000.00),
(105, 'Rohit', 8000.00);

DELIMITER //

CREATE PROCEDURE WithdrawMoney(
    IN p_account_no INT,
    IN p_amount DECIMAL(10,2)
)
BEGIN
    DECLARE v_balance DECIMAL(10,2);
    DECLARE v_account_found BOOLEAN DEFAULT TRUE;

    DECLARE CONTINUE HANDLER FOR NOT FOUND
        SET v_account_found = FALSE;

    IF p_amount <= 0 THEN
        SELECT 'Error: Withdrawal amount must be greater than zero.' AS Message;
    ELSE
        SELECT Balance
        INTO v_balance
        FROM Account
        WHERE Account_No = p_account_no;

        IF v_account_found = FALSE THEN
            SELECT 'Error: Account does not exist.' AS Message;
        ELSEIF p_amount > v_balance THEN
            SELECT 'Error: Insufficient balance.' AS Message;
        ELSE
            UPDATE Account
            SET Balance = Balance - p_amount
            WHERE Account_No = p_account_no;

            SELECT 'Withdrawal successful.' AS Message;
        END IF;
    END IF;
END //

DELIMITER ;

-- Successful withdrawal
CALL WithdrawMoney(101, 2000.00);

-- Test account not found (uncomment to test)
-- CALL WithdrawMoney(999, 1000.00);

-- Test insufficient balance (uncomment to test)
-- CALL WithdrawMoney(101, 50000.00);

-- Test invalid amount (uncomment to test)
-- CALL WithdrawMoney(101, -500.00);

SELECT * FROM Account;
