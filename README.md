# SQL-Intern-task-7 Creating Views
## Objective
 how to create and use views in SQL:
 Simplifying complex queries.
 Reusing logic across applications.
 Improving abstraction and data security.
## Tools Used
DB Browser for SQLite 
MYSQL Workbench
## What is a View?
A View is a virtual table in SQL that is created using a SELECT query.
It does not store data but displays the result dynamically every time it's queried.
## CREATE Sample Table 
CREATE TABLE employees (
    emp_id INTEGER PRIMARY KEY,
    name TEXT,
    department TEXT,
    salary REAL
);

INSERT INTO employees VALUES 
(1, 'Arun', 'HR', 40000),
(2, 'Meena', 'IT', 65000),
(3, 'Raj', 'IT', 70000),
(4, 'Kavi', 'Finance', 45000);

## Views Created
1. it_employees
 Shows only employees from the IT department.

CREATE VIEW it_employees AS
SELECT emp_id, name, salary
FROM employees
WHERE department = 'IT';

2.salary_with_bonus
Calculates and displays a 10% bonus based on salary.

CREATE VIEW salary_with_bonus AS
SELECT name, salary, salary * 0.10 AS bonus
FROM employees;

3.high_salary_employees
Filters out employees earning more than ₹60,000.

CREATE VIEW high_salary_employees AS
SELECT name, department, salary
FROM employees
WHERE salary > 60000;

## How to Use the Views

SELECT * FROM it_employees;
SELECT * FROM salary_with_bonus;
SELECT * FROM high_salary_employees;

## Advantages of Using Views

| Benefit        | Explanation                                |
| -------------- | ------------------------------------------ |
| Reusability    | Write once, use anywhere                   |
| Simplification | Hides complex logic                        |
| Abstraction    | Shows only required data                   |
| Security       | Restricts access to sensitive columns/rows |

## Drop the view (if needed)

DROP VIEW salary_with_bonus;

## Outcomes
1. Learned the concept of views in SQL and their real-world applications.

2. Practiced creating views using simple and complex SELECT queries.

3. Understood how to perform calculations (like bonuses) directly within a view.

4. Applied filters and conditions to present targeted data using views.

5. Experienced how views improve query reusability, readability, and security.

6. Understood how views help in data abstraction by exposing only the necessary information.



