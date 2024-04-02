Here are the SQL queries for the practice exercises using the `Customers`, `Products`, and `Orders` tables.

1. **Calculate the total amount spent by each customer:**
   ```sql
   SELECT CustomerID, SUM(TotalAmount) AS TotalSpent
   FROM Orders
   GROUP BY CustomerID;
   ```
   This query groups all orders by `CustomerID` and sums up the `TotalAmount` for each customer to find out the total spent by each one.

2. **Find out how many different products have been ordered in total:**
   Assuming there's an `OrderDetails` or similar table that records each product in each order, you would use:
   ```sql
   SELECT COUNT(DISTINCT ProductID) AS NumberOfUniqueProductsOrdered
   FROM OrderDetails;
   ```
   This query counts the distinct `ProductID` entries in the `OrderDetails` table to determine the number of different products that have been ordered.
