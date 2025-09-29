1. What is GROUP BY?

It groups rows based on one or more columns so aggregate functions (COUNT, SUM, AVG, etc.) can be applied.

SELECT department_id, AVG(salary)
FROM employees
GROUP BY department_id;


2. Difference between WHERE and HAVING?

WHERE → filters rows before grouping.

HAVING → filters groups after aggregation.

SELECT department_id, COUNT(*)
FROM employees
WHERE salary > 50000      -- row filter
GROUP BY department_id
HAVING COUNT(*) > 5;      -- group filter


3. How does COUNT(*) differ from COUNT(column)?

COUNT(*) → counts all rows (including NULLs).

COUNT(column) → counts non-NULL values only in that column.

4. Can you group by multiple columns?
✅ Yes. Example:

SELECT department_id, job_id, AVG(salary)
FROM employees
GROUP BY department_id, job_id;


5. What is ROUND() used for?

It rounds a numeric value to a specified number of decimal places.

SELECT ROUND(123.456, 2);  -- 123.46


6. How do you find the highest salary by department?

SELECT department_id, MAX(salary) AS highest_salary
FROM employees
GROUP BY department_id;


7. What is the default behavior of GROUP BY?

It groups rows in ascending order by the grouped column(s).

Each unique combination of column values becomes one group.

8. Explain AVG and SUM.

AVG(column) → returns the average value of a numeric column.

SUM(column) → returns the total sum of values in a numeric column.

9. How to count distinct values?

SELECT COUNT(DISTINCT department_id) 
FROM employees;


→ Counts how many unique departments exist.

10. What is an aggregate function?

A function that operates on a group of rows and returns a single value.

Examples: COUNT(), SUM(), AVG(), MAX(), MIN().
