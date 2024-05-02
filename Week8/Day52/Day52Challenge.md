### Day 52: Subqueries and Nested Queries

Welcome to Day 52! Today, we're diving into the world of subqueries and nested queries. These powerful SQL features allow you to embed one query within another, enabling you to perform complex operations and gain deeper insights from your data.

#### Understanding Subqueries

Subqueries, also known as nested queries or inner queries, are SQL queries embedded within another SQL statement. They can be used in various parts of a query such as `SELECT`, `FROM`, or `WHERE` clauses.

Subqueries are particularly useful when you need to:

- Retrieve data based on the result of another query.
- Perform calculations or comparisons using the output of a subquery.
- Filter data dynamically based on conditions.

Let's explore how subqueries can be utilized in different contexts.

#### Practice with Examples

**1. Subquery in SELECT Clause:**
```sql
SELECT Name, (SELECT COUNT(*) FROM Orders WHERE Orders.CustomerID = Customers.CustomerID) AS OrderCount
FROM Customers;
```
In this example, the subquery calculates the count of orders for each customer, and this count is returned as a column alongside customer names.

**2. Subquery in FROM Clause:**
```sql
SELECT *
FROM (SELECT Name, Age FROM Employees WHERE Department = 'Sales') AS SalesEmployees;
```
Here, the subquery selects employees from the Sales department, and the outer query then retrieves all columns from this result set.

**3. Subquery in WHERE Clause:**
```sql
SELECT Name, Age
FROM Employees
WHERE Age > (SELECT AVG(Age) FROM Employees);
```
This query selects employees whose age is greater than the average age of all employees, utilizing a subquery within the `WHERE` clause for comparison.

#### Assessment

Now, it's time to test your understanding of subqueries by solving the following tasks:

1. Write a query to retrieve the names of customers who have placed more than two orders.
2. Create a query to find the departments where the average salary is higher than the overall average salary.
3. Fetch the details of employees who have a salary greater than the average salary of their respective departments.

Mastering subqueries allows you to perform intricate analyses and gain valuable insights from your database. Let's put your skills to the test!

## Keep Exploring:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)