### Day 55: Introduction to Data Types and Constraints

Welcome to Day 55! Today, we're exploring data types and constraints in SQL, essential elements for defining the structure and integrity of your database.

#### Data Types in SQL

Data types specify the type of data that can be stored in a column of a table. Different SQL database systems support various data types, but common ones include:

1. **Numeric Types:** Integers (`INT`, `BIGINT`), floating-point numbers (`FLOAT`, `REAL`, `DOUBLE PRECISION`), fixed-point numbers (`NUMERIC`, `DECIMAL`).
  
2. **Character String Types:** Fixed-length strings (`CHAR`), variable-length strings (`VARCHAR`, `TEXT`).

3. **Date and Time Types:** Date (`DATE`), time (`TIME`), date and time (`DATETIME`, `TIMESTAMP`), interval.

4. **Boolean Type:** `BOOLEAN`.

5. **Binary Types:** Binary large objects (`BLOB`), character large objects (`CLOB`), binary data (`BINARY`, `VARBINARY`).

#### Constraints in SQL

Constraints enforce rules on the data in a table, ensuring data integrity and consistency. Common constraints include:

1. **NOT NULL:** Ensures that a column cannot contain null values, i.e., every row must have a value for that column.
  
2. **UNIQUE:** Ensures that all values in a column are unique, except for null values if the column allows them.

3. **PRIMARY KEY:** A combination of `NOT NULL` and `UNIQUE`, uniquely identifies each row in a table. There can be only one primary key per table.

4. **FOREIGN KEY:** Establishes a link between data in two tables, enforcing referential integrity. The values in the foreign key column(s) of one table must match the values in the primary key column(s) of another table.

5. **CHECK:** Specifies a condition that must be met for values in a column. It ensures that only values satisfying the condition are allowed.

#### Assessment

To reinforce your understanding, consider the following tasks:

1. Identify the appropriate data types for the following columns: `Name`, `Age`, `Salary`, `JoiningDate`, `IsEmployed`.
2. Determine the constraints needed for a table representing employees' information. Consider constraints such as `NOT NULL` for `Name` and `JoiningDate`, `UNIQUE` for `EmployeeID`, and `FOREIGN KEY` for `DepartmentID` referencing the `Departments` table.
3. Explain the importance of using constraints to maintain data integrity in a database.

By completing these tasks, you'll gain practical insight into how data types and constraints contribute to the design and integrity of a database schema.

## Keep Exploring:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)