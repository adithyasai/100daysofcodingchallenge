# Day 48: Grouping Data with GROUP BY in SQL

## Understanding GROUP BY

The `GROUP BY` statement in SQL is used to arrange identical data into groups. This clause comes in handy when, along with aggregate functions, you want to summarize or aggregate data by categories.

### Why Use GROUP BY?
- To categorize data into groups based on one or more columns.
- To apply aggregate functions like `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()` to each group rather than the entire dataset.

### Using GROUP BY

**Syntax:**
```sql
SELECT column_name(s), AGGREGATE_FUNCTION(column_name)
FROM table_name
WHERE condition
GROUP BY column_name(s);
```

### Practice with GROUP BY

Let's use the `GROUP BY` clause to aggregate data on the sample online store database. The database has tables for customers, products, and orders.

1. **Total Number of Orders Per Customer:**
   ```sql
   SELECT CustomerID, COUNT(OrderID) AS NumberOfOrders
   FROM Orders
   GROUP BY CustomerID;
   ```
   This query groups orders by the `CustomerID` and counts the number of orders each customer has made.

2. **Average Price of Products Sold:**
   ```sql
   SELECT AVG(Price) AS AveragePrice
   FROM Products;
   ```
   Here, we calculate the average price across all products.

3. **Total Sales Per Product:**
   Assuming we have a `Sales` table that records each sale with a `ProductID` and an `Amount`, you would use:
   ```sql
   SELECT ProductID, SUM(Amount) AS TotalSales
   FROM Sales
   GROUP BY ProductID;
   ```
   This query will show the total sales amount for each product.

### Assessment

Now, using the provided tables (`Customers`, `Products`, and `Orders`), try the following exercises:

- Calculate the total amount spent by each customer.
- Find out how many different products have been ordered in total.

With these exercises, you'll be able to see how `GROUP BY` can turn a simple dataset into meaningful insights by summarizing data in various ways.

**Follow us:**

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)
