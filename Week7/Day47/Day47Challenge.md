# Day 47: Introduction to Functions and Aggregation in SQL

## SQL Aggregate Functions

Understanding and utilizing SQL aggregate functions allows you to compute a single result from a set of input values. These functions are crucial when you need to summarize or analyze large volumes of data.

### Getting to Know Basic Aggregate Functions

- `COUNT()`: Counts the number of rows that match the specified criteria.
- `MAX()`: Finds the highest value in a column.
- `MIN()`: Finds the lowest value in a column.
- `AVG()`: Calculates the average value of a column.
- `SUM()`: Adds together all the values in a column.

```sql
-- Example of COUNT()
SELECT COUNT(CustomerID) FROM Customers;

-- Example of MAX()
SELECT MAX(Price) FROM Products;

-- Example of MIN()
SELECT MIN(Price) FROM Products;

-- Example of AVG()
SELECT AVG(TotalAmount) FROM Orders;

-- Example of SUM()
SELECT SUM(TotalAmount) FROM Orders;
```

### Applying Aggregate Functions to Aggregate Data

Aggregate functions can help answer questions like "How many orders have been placed?" or "What is the total revenue generated?".

- To find out how many customers are in the database:
  ```sql
  SELECT COUNT(*) AS NumberOfCustomers FROM Customers;
  ```
- To determine the most expensive product:
  ```sql
  SELECT MAX(Price) AS HighestPricedProduct FROM Products;
  ```
- To identify the product with the smallest stock quantity:
  ```sql
  SELECT MIN(StockQuantity) AS LeastStockedProduct FROM Products;
  ```
- To calculate the average order size in terms of amount:
  ```sql
  SELECT AVG(TotalAmount) AS AverageOrderSize FROM Orders;
  ```
- To calculate the total revenue from all orders:
  ```sql
  SELECT SUM(TotalAmount) AS TotalRevenue FROM Orders;
  ```

## Assessment

With your understanding of aggregate functions, use the provided `Customers`, `Products`, and `Orders` tables to perform a series of SQL queries:

1. How many products have a stock quantity greater than 50?
2. What is the average price of all products?
3. How many orders were placed in the last year?
4. What is the total sales amount for the current month?

Evaluate your queries to ensure accuracy, and make sure they execute successfully on your sample database.

**Remember:** Aggregate functions ignore `NULL` values, so your results only account for rows with non-NULL data in the aggregated column.

**Follow us:**

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)