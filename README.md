# SQL-Developer-Task2
CREATE TABLE Employees (
    emp_id INTEGER PRIMARY KEY,
    name TEXT NOT NULL,
    department TEXT,
    salary INTEGER,
    email TEXT UNIQUE
);

-- Normal insert
INSERT INTO Employees (emp_id, name, department, salary, email)
VALUES (1, 'Arjun', 'IT', 45000, 'arjun@example.com');

-- Insert with NULL values
INSERT INTO Employees (emp_id, name, department, salary, email)
VALUES (2, 'Keerthi', NULL, 38000, 'keerthi@example.com');

-- Partial Insert (missing columns become NULL)
INSERT INTO Employees (emp_id, name)
VALUES (3, 'Suresh');

-- Insert multiple rows
INSERT INTO Employees (emp_id, name, department, salary, email) VALUES
(4, 'Meena', 'HR', 50000, 'meena@example.com'),
(5, 'Raju', 'Finance', NULL, NULL);

-- Update a single row
UPDATE Employees
SET salary = 55000
WHERE emp_id = 4;

-- Update multiple rows
UPDATE Employees
SET department = 'General'
WHERE department IS NULL;

-- Delete a single record
DELETE FROM Employees
WHERE emp_id = 5;

-- Delete multiple rows
DELETE FROM Employees
WHERE salary IS NULL;

BEGIN TRANSACTION;

DELETE FROM Employees
WHERE emp_id = 2;

ROLLBACK;   -- This restores the deleted row
