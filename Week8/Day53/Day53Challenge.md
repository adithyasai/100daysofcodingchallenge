### Day 53: Data Manipulation Language (DML)

Welcome to Day 53 of our SQL journey! Today, we're delving into Data Manipulation Language (DML), which includes commands for inserting, updating, and deleting data within a database.

#### Introduction to DML

DML commands are crucial for managing the data stored in your database tables. They allow you to perform the following operations:

- **INSERT:** Adds new rows of data into a table.
- **UPDATE:** Modifies existing data within a table.
- **DELETE:** Removes rows of data from a table.

Let's explore each of these DML commands in detail.

#### INSERT Statement

The `INSERT` statement is used to add new records (rows) to a table.

**Syntax:**
```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

**Example:**
```sql
INSERT INTO Customers (Name, Email)
VALUES ('John Doe', 'john@example.com');
```

This command inserts a new customer with the name "John Doe" and email "john@example.com" into the `Customers` table.

#### UPDATE Statement

The `UPDATE` statement is used to modify existing records in a table.

**Syntax:**
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

**Example:**
```sql
UPDATE Customers
SET Email = 'new_email@example.com'
WHERE Name = 'John Doe';
```

This command updates the email address of the customer named "John Doe" to "new_email@example.com".

#### DELETE Statement

The `DELETE` statement is used to remove records from a table.

**Syntax:**
```sql
DELETE FROM table_name
WHERE condition;
```

**Example:**
```sql
DELETE FROM Customers
WHERE Name = 'John Doe';
```

This command deletes the customer named "John Doe" from the `Customers` table.

#### Assessment

Now, it's time to apply your knowledge of DML commands:

1. Insert a new product into the `Products` table with the name "Laptop" and price $999.
2. Update the price of all products in the `Products` table manufactured by "Apple" to $1499.
3. Delete all orders from the `Orders` table where the order date is before January 1, 2023.

Put these DML commands into action to manipulate the data in your database effectively!

## Keep Practicing:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)