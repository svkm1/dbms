-- PRACTICAL 1: Library database - DDL and DML
CREATE DATABASE IF NOT EXISTS Library;
USE Library;

DROP TABLE IF EXISTS Books;

CREATE TABLE Books (
    Book_ID INT PRIMARY KEY,
    Book_Name VARCHAR(50),
    Author VARCHAR(50),
    Price DECIMAL(10,2),
    Quantity INT
);

INSERT INTO Books VALUES
(1, 'Python Basics', 'John', 450.00, 10),
(2, 'Java Programming', 'James', 650.00, 5),
(3, 'DBMS Concepts', 'Korth', 550.00, 8),
(4, 'C Programming', 'Dennis', 350.00, 12),
(5, 'Web Development', 'Peter', 700.00, 6);

-- Display all records
SELECT * FROM Books;

-- Update the price of a particular book
UPDATE Books
SET Price = 750.00
WHERE Book_ID = 2;

-- Delete a particular book
DELETE FROM Books
WHERE Book_ID = 4;

-- Add a new column
ALTER TABLE Books
ADD Publisher VARCHAR(50);

-- Display books with price greater than 500
SELECT * FROM Books
WHERE Price > 500;
