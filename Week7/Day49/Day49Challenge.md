# Day 49: Review and Practice

Today is about reinforcing the SQL concepts learned over the week. It's essential to review to ensure a solid understanding and ability to apply SQL to real-world problems.

## Review of the Week's Concepts

1. **SELECT and WHERE Clauses**
   Revisit how to query data from a table and filter it based on specific criteria.

2. **ORDER BY and LIMIT**
   Recall the methods for sorting your result sets and limiting the number of records returned.

3. **Aggregate Functions**
   Ensure you understand how to use `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()`.

4. **GROUP BY Clause**
   Review how to group rows that have the same values in specified columns into summary rows.

5. **Complex Queries**
   Practice combining the above concepts to write more complex SQL queries.

#### Tasks

##### Task 1: Customers Table - Count by Region
Assuming your `Customers` table has an `Address` column that contains city information, count how many customers are from each city.
```sql
SELECT SUBSTRING(Address, LOCATE(',', Address) + 1) AS City, COUNT(*) AS NumberOfCustomers
FROM Customers
GROUP BY City;
```

##### Task 2: Products Table - Price Range Summary
Determine the number of products that fall into different price ranges (e.g., 0-50, 51-100, etc.).
```sql
SELECT
  CASE 
    WHEN Price BETWEEN 0 AND 50 THEN '0-50'
    WHEN Price BETWEEN 51 AND 100 THEN '51-100'
    ELSE '101+'
  END AS PriceRange,
  COUNT(*) AS NumberOfProducts
FROM Products
GROUP BY PriceRange;
```

##### Task 3: Orders Table - Monthly Sales Totals
Calculate the total sales amount for each month, assuming `OrderDate` is in a format that can be sorted (e.g., YYYY-MM-DD).
```sql
SELECT SUBSTRING(OrderDate, 1, 7) AS OrderMonth, SUM(TotalAmount) AS MonthlySales
FROM Orders
GROUP BY OrderMonth;
```

##### Task 4: Products Table - Average Price of All Products
Calculate the average price of all products listed in the `Products` table.
```sql
SELECT AVG(Price) AS AverageProductPrice
FROM Products;
```

##### Task 5: Orders Table - Order Count by Date
Count the number of orders placed on each date.
```sql
SELECT OrderDate, COUNT(*) AS TotalOrders
FROM Orders
GROUP BY OrderDate;
```

**Follow us:**

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)