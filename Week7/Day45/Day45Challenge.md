### Day 45: Basic SQL Queries

Today, we're going to learn about retrieving data from a SQL database using `SELECT` statements and how to filter that data using `WHERE` clauses. We'll be practicing these queries on a sample database.

#### Using SELECT
The `SELECT` statement is used to select data from a database. The data returned is stored in a result table, sometimes called the result-set.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name;
```

**Example:**
Let's say we have a table named `Customers`. If you want to select the name and email address of all customers, you would use:
```sql
SELECT Name, Email
FROM Customers;
```

If you want to select all columns, you can use the asterisk (*) shorthand:
```sql
SELECT *
FROM Customers;
```

#### Using WHERE
The `WHERE` clause is used to filter records. It is used to extract only those records that fulfill a specified condition.

**Syntax:**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

**Example:**
If you want to find the customer named "Alice Smith" in the Customers table, you would use:
```sql
SELECT *
FROM Customers
WHERE Name = 'Alice Smith';
```

#### Practice with Examples on a Sample Database

**1. Selecting Specific Columns:**
Let's select the `UserID` and `Name` of all users from the `Users` table.
```sql
SELECT UserID, Name
FROM Users;
```

**2. Using WHERE to Filter Results:**
To get the details of users who have a UserID less than 5:
```sql
SELECT *
FROM Users
WHERE UserID < 5;
```

**3. Combining Conditions:**
You can also combine conditions using `AND` or `OR`. For example, to select users with a `UserID` less than 5 and the name "Alice Smith":
```sql
SELECT *
FROM Users
WHERE UserID < 5 AND Name = 'Alice Smith';
```

**4. Practice with LIKE:**
The `LIKE` clause is used in a `WHERE` clause to search for a specified pattern in a column.

For example, to find users whose names start with 'Al':
```sql
SELECT *
FROM Users
WHERE Name LIKE 'Al%';
```
In SQL, `%` represents zero or more characters. The `LIKE` clause can also use `_`, which represents a single character.

**5. Sorting Results:**
You can sort the results using `ORDER BY`. For example, to get all users sorted by name in ascending order:
```sql
SELECT *
FROM Users
ORDER BY Name;
```

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)