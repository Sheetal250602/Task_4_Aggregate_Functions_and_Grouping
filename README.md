# Task_4_Aggregate_Functions_and_Grouping
# Using Database 'COMPANY' and new table 'EMPLOYEES' for aggregate functions(COUNT, SUM, MIN, MAX, AVG) and filter groups using HAVING clause.

CREATE DATABASE COMPANY;
USE COMPANY;

CREATE TABLE Employees(
employee_id INT PRIMARY KEY NOT NULL,
first_name VARCHAR(50),
last_name VARCHAR(50),
category VARCHAR(50),
department VARCHAR(50),
salary FLOAT DEFAULT 20000,
joining_date DATE
);

INSERT INTO Employees VALUES
(1, 'John', 'Smith', 'Full Time', 'Engineering', 80000, '2021-01-29'),
(2, 'Alice', 'Johnson', 'Part Time', 'HR', 30000.00, '2021-05-12'),
(3, 'Bob', 'Brown', 'Full Time', 'Finance', 90000, '2021-01-29'),
(4, 'Carol', 'White', 'Contract', 'IT', 75000, '2021-01-01'),
(5, 'David', 'Green', 'Full Time', 'Engineering', 85000, '2022-01-13'),
(6, 'Emma', 'Blue', 'Part Time', 'Finance', 32000, '2023-01-01'),
(7, 'Frank', 'Black', 'Full Time', 'HR', 60000, '2024-05-05'),
(8, 'Grace', 'Grey', 'Full Time', 'Marketing', 70000, '2021-01-22'),
(9, 'Henry', 'Red', 'Contract', 'Sales', 95000, '2021-01-08'),
(10, 'Ivy', 'Yellow', 'Full Time', 'Marketing', 28000, '2025-01-03');

SELECT * FROM Employees;

# <img width="613" height="280" alt="image" src="https://github.com/user-attachments/assets/1e5f4da2-1cd3-4178-a08d-f2bd7c11a372" />

# COUNT Function:
SELECT COUNT(*) AS total_employees FROM Employees; 

# <img width="157" height="76" alt="image" src="https://github.com/user-attachments/assets/e8c393cb-c7f7-4ead-a2d9-e1e364b7fcb7" />

# SUM Function:
SELECT SUM(salary) AS total_salary FROM Employees;

# <img width="139" height="95" alt="image" src="https://github.com/user-attachments/assets/0b314a02-04b9-453c-865c-748910115877" />

# AVG Function:
SELECT AVG(salary) AS average_salary FROM Employees;

# <img width="156" height="84" alt="image" src="https://github.com/user-attachments/assets/1ff3a12b-91e4-4e8c-96d1-06429b5a578c" />

# MAX Function:
SELECT MAX(salary) AS Highest_salary FROM Employees;

# <img width="170" height="96" alt="image" src="https://github.com/user-attachments/assets/4e044dc6-51c9-4cc6-8db3-3bbb1f6b57a6" />

# MIN Function:
SELECT MIN(salary) AS Lowest_salary FROM Employees;

# <img width="167" height="81" alt="image" src="https://github.com/user-attachments/assets/388b7405-5172-415b-929b-9821fd020957" />

# GROUP BY Clause with COUNT Function:
SELECT department, COUNT(*) AS total_employees FROM employees
GROUP BY department;

# <img width="249" height="181" alt="image" src="https://github.com/user-attachments/assets/ddd4eab9-c9d4-4747-823a-85ecaa5e74c3" />

# GROUP BY Clause with SUM Function:
SELECT department, SUM(salary) FROM Employees
GROUP BY department;

# <img width="261" height="212" alt="image" src="https://github.com/user-attachments/assets/e0774697-e031-4fea-a0ae-301c02e5957d" />

# GROUP BY Clause with AVG Function:
SELECT department, AVG(salary) FROM Employees
GROUP BY department;

# <img width="243" height="205" alt="image" src="https://github.com/user-attachments/assets/e30ef4f1-cc33-4376-a98c-49a33ec95906" />

# GROUP BY Clause with MIN Function:
SELECT department, MIN(salary) FROM Employees
GROUP BY department;

# <img width="226" height="200" alt="image" src="https://github.com/user-attachments/assets/732eb209-67d1-4169-9c81-a592999751cf" />


# GROUP BY Clause with MAX Function:
SELECT department, MAX(salary) FROM Employees
GROUP BY department;

# <img width="234" height="198" alt="image" src="https://github.com/user-attachments/assets/b91a5e73-823e-41ec-90de-44ed4d6e0972" />



# GROUP BY Clause with COUNT Function Using HAVING clause:
SELECT department, COUNT(*) AS total_employees FROM Employees
GROUP BY department
HAVING department = 'Engineering';

# <img width="272" height="91" alt="image" src="https://github.com/user-attachments/assets/0885de1f-5c38-4a7f-ac5c-45e15fc1336e" />

# GROUP BY Clause with AVG Function Using HAVING clause:
SELECT category, AVG(salary) AS avg_salary FROM Employees
GROUP BY category
HAVING category = 'Full Time';

# <img width="255" height="88" alt="image" src="https://github.com/user-attachments/assets/cc511fb9-4992-4535-ba75-efb1e6cfd428" />

#  GROUP BY Clause with MIN Function Using HAVING clause:
SELECT category, MIN(salary) AS total_salary FROM Employees
GROUP BY category
HAVING category = 'Part Time';

# <img width="257" height="100" alt="image" src="https://github.com/user-attachments/assets/6fec62d1-9023-4b74-b59d-a00602208d88" />

# GROUP BY Clause with MAX Function Using HAVING clause:
SELECT category, MAX(salary) AS total_salary FROM Employees
GROUP BY category
HAVING category = 'Part Time';

# <img width="235" height="98" alt="image" src="https://github.com/user-attachments/assets/8741b3ab-005b-4473-bf44-6d19c80f7bff" />

# GROUP BY Clause with SUM Function Using HAVING clause:
SELECT category, SUM(salary) AS total_salary FROM Employees
GROUP BY category
HAVING category = 'Part Time';

# <img width="238" height="93" alt="image" src="https://github.com/user-attachments/assets/94c9014d-b9fc-4e04-98d6-33047a8ad949" />

# Finding Number of Columns by using COUNT Function:
SELECT COUNT(*) AS total_columns
FROM INFORMATION_SCHEMA.COLUMNS
WHERE TABLE_NAME = 'Employees';

# <img width="154" height="108" alt="image" src="https://github.com/user-attachments/assets/fcb5caae-cfe8-48f4-8e1b-d05fe463e49c" />

# ROUND Function:
SELECT category, ROUND(AVG(salary), 2) AS avg_salary FROM Employees
GROUP BY category
HAVING category = 'Full Time';

# <img width="245" height="106" alt="image" src="https://github.com/user-attachments/assets/28bd2ecb-c4eb-496a-92ae-a99d19e75629" />










