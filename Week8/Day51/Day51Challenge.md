### Day 51: Exploring Different Types of Joins

Welcome back to Day 51 of our SQL journey! Today, we're expanding our knowledge of joins by exploring three additional types: `LEFT JOIN`, `RIGHT JOIN`, and `FULL JOIN`.

#### Understanding Different Join Types

Each join type offers unique capabilities for combining data from multiple tables.

- **LEFT JOIN:** Returns all records from the left table (table1), and the matched records from the right table (table2). If there is no match, NULL values are returned from the right side.

- **RIGHT JOIN:** Returns all records from the right table (table2), and the matched records from the left table (table1). If there is no match, NULL values are returned from the left side.

- **FULL JOIN:** Returns all records when there is a match in either left (table1) or right (table2) table. If there is no match, NULL values are returned from the side that has no match.

Let's delve into examples of each type to grasp their functionalities.

#### Practice with Examples

**1. LEFT JOIN:**
```sql
SELECT Orders.OrderID, Customers.Name
FROM Orders
LEFT JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```

This query retrieves all orders, along with the corresponding customer names. Even if a customer hasn't placed any orders, their name will still appear with NULL values for order-related columns.

**2. RIGHT JOIN:**
```sql
SELECT Orders.OrderID, Customers.Name
FROM Orders
RIGHT JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```

Here, we're fetching all customers, including those who haven't placed any orders yet. Order-related columns will display NULL values for customers who haven't made any purchases.

**3. FULL JOIN:**
```sql
SELECT Orders.OrderID, Customers.Name
FROM Orders
FULL JOIN Customers ON Orders.CustomerID = Customers.CustomerID;
```

This query returns all orders and all customers. If a customer hasn't placed any orders or an order doesn't have a corresponding customer, NULL values will appear in the result set.

#### Assessment

Now it's time to put your newfound knowledge to the test! Write queries that utilize different join types to:

1. Retrieve all orders along with the corresponding customer information, including those without any associated customers.
2. Fetch all customers, displaying their orders if available, and including customers who haven't made any purchases.
3. Combine data from two tables, showing all matches and non-matches from both sides.

Mastering different join types opens up a plethora of possibilities for querying complex datasets. Happy querying!

## Keep Exploring:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)