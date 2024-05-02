### Day 56: Review and Hands-on Project

#### Review

Take some time to review all the topics you've covered so far, including:

- SQL fundamentals such as SELECT statements, WHERE clauses, ORDER BY, and LIMIT.
- Aggregate functions like COUNT, MAX, MIN, AVG.
- GROUP BY for grouping data.
- Different types of joins including INNER JOIN, LEFT JOIN, RIGHT JOIN, and FULL JOIN.
- Subqueries and nested queries.
- Data Manipulation Language (DML) commands: INSERT, UPDATE, DELETE.
- Database design principles including data types and constraints.

#### Hands-on Project: Sample Database

Let's create a simple hands-on project with a sample database schema and sample data. This project will include four tables: `Employees`, `Departments`, `Projects`, and `Assignments`.

**Database Schema:**

1. `Employees`:
   - EmployeeID (Primary Key)
   - Name
   - Age
   - DepartmentID (Foreign Key)

2. `Departments`:
   - DepartmentID (Primary Key)
   - DepartmentName

3. `Projects`:
   - ProjectID (Primary Key)
   - ProjectName

4. `Assignments`:
   - AssignmentID (Primary Key)
   - EmployeeID (Foreign Key)
   - ProjectID (Foreign Key)
   - HoursWorked

**Sample Data Insertion:**

Here are the insert statements for each table with sample data:

```sql
-- Employees
INSERT INTO Employees (Name, Age, DepartmentID) VALUES
('John Doe', 30, 1),
('Alice Smith', 28, 2),
('Bob Johnson', 35, 1),
('Emily Davis', 32, 3),
('Michael Brown', 27, 2),
('Jessica Miller', 31, 1),
('David Wilson', 29, 3),
('Jennifer Martinez', 33, 2),
('Daniel Taylor', 26, 1),
('Sarah Anderson', 34, 3),
('Matthew Thomas', 29, 2),
('Laura White', 36, 1),
('Christopher Harris', 32, 3),
('Megan Lee', 28, 1),
('Ryan Clark', 30, 2),
('Kimberly Turner', 33, 1),
('James Rodriguez', 27, 3),
('Amanda Scott', 31, 2),
('Joshua King', 34, 1),
('Olivia Green', 25, 3);

-- Departments
INSERT INTO Departments (DepartmentName) VALUES
('HR'),
('Finance'),
('IT'),
('Marketing'),
('Operations'),
('Sales'),
('Engineering'),
('Customer Service'),
('Research and Development'),
('Legal'),
('Quality Assurance'),
('Purchasing'),
('Production'),
('Administration'),
('Logistics'),
('Facilities Management'),
('Training'),
('Public Relations'),
('Design'),
('Consulting');

-- Projects
INSERT INTO Projects (ProjectName) VALUES
('Website Redesign'),
('Financial Analysis Tool'),
('Database Migration'),
('Mobile App Development'),
('Marketing Campaign'),
('Inventory Management System'),
('Product Launch'),
('Customer Satisfaction Survey'),
('Research Project'),
('Legal Compliance Review'),
('Quality Control Initiative'),
('Procurement Automation'),
('Production Optimization'),
('Office Renovation'),
('Supply Chain Management'),
('Training Program Development'),
('Publicity Event'),
('Graphic Design Project'),
('Consulting Services'),
('Software Integration');

-- Assignments
INSERT INTO Assignments (EmployeeID, ProjectID, HoursWorked) VALUES
(1, 1, 40),
(2, 2, 30),
(3, 1, 45),
(4, 3, 35),
(5, 4, 28),
(6, 5, 38),
(7, 6, 42),
(8, 7, 25),
(9, 8, 40),
(10, 9, 32),
(11, 10, 36),
(12, 11, 30),
(13, 12, 45),
(14, 13, 37),
(15, 14, 39),
(16, 15, 28),
(17, 16, 35),
(18, 17, 31),
(19, 18, 40),
(20, 19, 33);
```

#### Assessment Questions:

1. Write a SQL query to retrieve the names of all employees in the IT department.
2. Calculate the total number of hours worked on the "Website Redesign" project.
3. Find the average age of employees in each department.
4. List the names of employees who have not been assigned to any project.
5. Retrieve the department name along with the total number of employees in each department.
6. Update the age of the employee named "Alice Smith" to 29.
7. Delete all assignments where the number of hours worked is less than 20.
8. Explain the importance of using foreign key constraints in maintaining data integrity in a database.

Take your time to answer these questions, and feel free to experiment with additional queries to further strengthen your skills!

Happy querying!

## Keep Exploring:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)