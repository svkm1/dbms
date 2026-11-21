-- PRACTICAL 9: Product operations using stored procedures
CREATE DATABASE IF NOT EXISTS Shop;
USE Shop;

DROP PROCEDURE IF EXISTS DisplayProducts;
DROP PROCEDURE IF EXISTS InsertProduct;
DROP PROCEDURE IF EXISTS UpdateProductPrice;
DROP PROCEDURE IF EXISTS DeleteProduct;
DROP TABLE IF EXISTS Product;

CREATE TABLE Product (
    Product_ID INT PRIMARY KEY,
    Product_Name VARCHAR(50),
    Price DECIMAL(10,2),
    Quantity INT
);

INSERT INTO Product VALUES
(1, 'Laptop', 50000.00, 10),
(2, 'Mouse', 500.00, 20),
(3, 'Keyboard', 1000.00, 15),
(4, 'Monitor', 12000.00, 8),
(5, 'Printer', 8000.00, 5);

DELIMITER //

-- 1. Display all products
CREATE PROCEDURE DisplayProducts()
BEGIN
    SELECT * FROM Product;
END //

-- 2. Insert a product
CREATE PROCEDURE InsertProduct(
    IN p_id INT,
    IN p_name VARCHAR(50),
    IN p_price DECIMAL(10,2),
    IN p_quantity INT
)
BEGIN
    INSERT INTO Product
    VALUES (p_id, p_name, p_price, p_quantity);
END //

-- 3. Update product price
CREATE PROCEDURE UpdateProductPrice(
    IN p_id INT,
    IN p_new_price DECIMAL(10,2)
)
BEGIN
    UPDATE Product
    SET Price = p_new_price
    WHERE Product_ID = p_id;
END //

-- 4. Delete a product
CREATE PROCEDURE DeleteProduct(
    IN p_id INT
)
BEGIN
    DELETE FROM Product
    WHERE Product_ID = p_id;
END //

DELIMITER ;

-- Execute the procedures
CALL DisplayProducts();
CALL InsertProduct(6, 'Headphones', 2000.00, 12);
CALL UpdateProductPrice(2, 700.00);
CALL DeleteProduct(5);
CALL DisplayProducts();
