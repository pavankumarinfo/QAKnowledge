## Inner Join: Returns only the rows that have matching values in both tables.

    Example:

    sql

    SELECT *
    FROM customers
    INNER JOIN orders
    ON customers.customer_id = orders.customer_id;

## Left Join: Returns all the rows from the left table and the matching rows from the right table. If there are no matching rows in the right table, the result will contain NULL values.

    Example:

    sql

    SELECT *
    FROM customers
    LEFT JOIN orders
    ON customers.customer_id = orders.customer_id;

## Right Join: Returns all the rows from the right table and the matching rows from the left table. If there are no matching rows in the left table, the result will contain NULL values.

    Example:

    sql

    SELECT *
    FROM customers
    RIGHT JOIN orders
    ON customers.customer_id = orders.customer_id;

## Full Outer Join: Returns all the rows from both tables, including the rows that do not have matching values in the other table. If there are no matching values, the result will contain NULL values.

    Example:

    sql

    SELECT *
    FROM customers
    FULL OUTER JOIN orders
    ON customers.customer_id = orders.customer_id;
    
## What is normalization and how does it relate to database design?
   Answer: Normalization is a process of organizing data in a database to reduce redundancy and improve data integrity. It helps to eliminate data anomalies and inconsistencies. Normalization is usually achieved by splitting a table into two or more tables, based on their functional dependencies.

## What is a foreign key and how is it used in SQL?
   Answer: A foreign key is a column or a set of columns that refers to a primary key in another table. It is used to establish a relationship between two tables in a relational database. The foreign key ensures that the data in the referencing table corresponds to the data in the referenced table.

## What is a join and what are the different types of joins in SQL?
   Answer: A join is used to combine data from two or more tables based on a common column. There are different types of joins in SQL, including inner join, left join, right join, and full outer join.

## What is a subquery and how is it used in SQL?
   Answer: A subquery is a query that is embedded within another query. It is used to retrieve data that will be used in the main query. A subquery can be used in different parts of a query, such as the SELECT, FROM, or WHERE clauses.

## How do you optimize SQL queries for performance?
   Answer: SQL query performance can be optimized by following best practices such as:

      Using indexes on frequently queried columns.
      Avoiding nested subqueries and correlated subqueries.
      Limiting the number of columns retrieved by the query.
      Using efficient join and filter conditions.
      Avoiding the use of functions in the WHERE clause.

## What is a stored procedure and how is it used in SQL?
   Answer: A stored procedure is a precompiled SQL code that is stored in the database and can be executed by calling it from an application or another SQL statement. Stored procedures can be used to perform complex database operations and can also be used to improve query performance.
   
## how many types of sub-query are available in sql and provide examples
There are several types of sub-queries in SQL. Here are some of the most commonly used types with examples:

  ###  Scalar sub-query: A scalar sub-query returns a single value, which can be used as an expression in the outer query. 
  For example:

    SELECT first_name, last_name, (SELECT MAX(salary) FROM employees) AS max_salary FROM employees;
    
    This query returns the first name, last name, and maximum salary from the employees table. The scalar sub-query (SELECT MAX(salary) FROM employees) returns a single value (the maximum salary) which is used as an expression in the outer query.

  ### Correlated sub-query: A correlated sub-query is a sub-query that refers to a column from the outer query. 
    
  For example:
            SELECT first_name, last_name
        FROM employees e
        WHERE salary > (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id);

    This query returns the first name and last name of employees whose salary is greater than the average salary of their department. The correlated sub-query (SELECT AVG(salary) FROM employees WHERE department_id = e.department_id) refers to the department ID column from the outer query.
    
  ### In-line view sub-query: An in-line view sub-query is a sub-query that is used as a table expression in the outer query. 
    
    For example:
        SELECT e.first_name, e.last_name, d.department_name
        FROM employees e, (SELECT * FROM departments WHERE department_name LIKE 'Sales%') d
        WHERE e.department_id = d.department_id;

        This query returns the first name, last name, and department name of employees who work in a department whose name starts with "Sales". The in-line view sub-query (SELECT * FROM departments WHERE department_name LIKE 'Sales%') is used as a table expression in the outer query.
        
        Overall, sub-queries are a powerful feature of SQL that allow you to perform complex queries and data analysis. By understanding the different types of sub-queries and how they can be used, you can write more efficient and effective SQL queries.

