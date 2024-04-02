
### Customers Table
This table will store information about the customers who purchase products from the online store.

**Columns:**
- `CustomerID`: A unique identifier for each customer (Primary Key).
- `FirstName`: The customer's first name.
- `LastName`: The customer's last name.
- `Email`: The customer's email address, which is also unique.
- `PhoneNumber`: The customer's phone number.
- `Address`: The customer's shipping address.

### Products Table
This table contains details about the products that are available for purchase in the online store.

**Columns:**
- `ProductID`: A unique identifier for each product (Primary Key).
- `ProductName`: The name of the product.
- `Description`: A brief description of the product.
- `Price`: The price of the product.
- `StockQuantity`: The number of units of the product in stock.

### Orders Table
This table records the details of customer orders.

**Columns:**
- `OrderID`: A unique identifier for each order (Primary Key).
- `CustomerID`: The identifier for the customer who placed the order (Foreign Key that references `CustomerID` in the Customers table).
- `OrderDate`: The date when the order was placed.
- `ShippingAddress`: The address where the order should be delivered (can be different from the address in the Customers table).
- `TotalAmount`: The total amount of the order.
