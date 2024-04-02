### Day 46: Sorting and Limiting Results

Sorting and limiting results are essential skills when you work with SQL. They help you make sense of the data by organizing it and letting you focus on specific subsets.

#### Using ORDER BY
The `ORDER BY` keyword is used to sort the result-set in ascending or descending order. The `ORDER BY` keyword sorts the records in ascending order by default. To sort the records in descending order, you can use the `DESC` keyword.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```

**Example:**
Imagine you have a table named `Products` with a `Price` column and you want to see the most expensive products first:
```sql
SELECT *
FROM Products
ORDER BY Price DESC;
```

#### Using LIMIT
The `LIMIT` clause is used to specify the maximum number of records the result-set will contain. This is useful for paging through results.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
LIMIT number;
```

**Example:**
If you want to get only the first 5 users from your `Users` table:
```sql
SELECT *
FROM Users
LIMIT 5;
```

#### Practice with the Sample Database

Let's apply both `ORDER BY` and `LIMIT` in practice with a sample database.

**1. Sort Customers by Name:**
```sql
SELECT Name, Email
FROM Customers
ORDER BY Name;
```
This will list all customers sorted alphabetically by their names.

**2. Get the Top 3 Most Expensive Products:**
```sql
SELECT ProductName, Price
FROM Products
ORDER BY Price DESC
LIMIT 3;
```
This query will show you the three most expensive products.

**3. Get the First 5 Orders:**
```sql
SELECT OrderID, TotalAmount
FROM Orders
ORDER BY OrderID
LIMIT 5;
```
This will retrieve the first five orders made, assuming `OrderID` is sequentially assigned.

**4. Combining WHERE, ORDER BY, and LIMIT:**
You might want to combine these clauses to get, for example, the next 5 orders starting from the 10th row, for orders greater than $50:
```sql
SELECT OrderID, TotalAmount
FROM Orders
WHERE TotalAmount > 50
ORDER BY OrderID
LIMIT 5 OFFSET 9;
```
The `OFFSET` keyword skips the first 9 records.

## Assignment: Data Analysis with Sorting and Limiting

Analyze a table Orders for a retail company. Use the `ORDER BY` and `LIMIT` clauses to answer the following questions:

1. What are the 5 least sold products?
2. List the second set of 10 transactions when ordered by date (use LIMIT and OFFSET)

Prepare SQL queries to retrieve this information, ensuring your results are clear and well-presented.

## LinkedIn Post for Achievement

"Day 46 of my coding journey, I’ve leveled up my SQL skills! From sorting complex data sets to extracting precise information with `LIMIT`, I’m unlocking the full potential of data management. #Day46 #100DaysOfCodingChallenge #SQL #DataSorting #codewithaadi"

**Follow us:**

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)