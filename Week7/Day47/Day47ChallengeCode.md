
1. **How many products have a stock quantity greater than 50?**
   ```sql
   SELECT COUNT(*) AS ProductsOverFifty
   FROM Products
   WHERE StockQuantity > 50;
   ```

2. **What is the average price of all products?**
   ```sql
   SELECT AVG(Price) AS AverageProductPrice
   FROM Products;
   ```

3. **How many orders were placed in the last year?**
   Assuming we are considering the last year from today's date, the query would look like this:
   ```sql
   SELECT COUNT(*) AS OrdersLastYear
   FROM Orders
   WHERE OrderDate >= CURRENT_DATE - INTERVAL '1 year';
   ```

4. **What is the total sales amount for the current month?**
   Again, assuming the current date's month, we would use:
   ```sql
   SELECT SUM(TotalAmount) AS TotalSalesCurrentMonth
   FROM Orders
   WHERE OrderDate >= DATE_TRUNC('month', CURRENT_DATE)
     AND OrderDate < DATE_TRUNC('month', CURRENT_DATE) + INTERVAL '1 month';
   ```
