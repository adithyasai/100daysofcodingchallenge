# Day 42 Assignment: Enhance Your Personal Expense Tracker

Building upon the foundational work from Day 41, today's assignment involves adding new features and enhancements to your Python-based Command-Line Personal Expense Tracker. This will deepen your understanding of Python and provide hands-on experience with more complex programming concepts.

## Assignment Objectives:

- **Implement Expense Categories:** Allow users to categorize their expenses (e.g., Food, Transport, Entertainment).
- **Monthly Expense Summary:** Provide a summary of expenses for a given month, including total spent and breakdown by category.
- **Search Expenses:** Implement a feature to search for expenses by description or category.
- **Data Validation:** Ensure that user inputs for amounts and dates are validated properly.

## Step-by-Step Guide:

### Step 1: Implement Expense Categories

1. **Modify the Expense Structure:**
   Update your expense entry structure to include a 'category' field.

2. **Update the Add Expense Function:**
   - When adding a new expense, prompt the user for the category.
   - Provide a list of predefined categories for the user to choose from or allow the creation of a new category.

### Step 2: Monthly Expense Summary

1. **Implement a Summary Function:**
   Create a function that asks the user for a year and month, then displays a summary of expenses for that month, including total expenditure and breakdown by category.

   ```python
   def monthly_summary():
       year = input("Enter the year (YYYY): ")
       month = input("Enter the month (MM): ")
       # Your code to calculate and display the summary
   ```

### Step 3: Search Expenses

1. **Implement Search Functionality:**
   Allow users to search their expenses based on description or category. This will involve filtering the list of expenses and displaying matching entries.

   ```python
   def search_expenses():
       search_query = input("Enter search term (description/category): ")
       # Your code to search and display matching expenses
   ```

### Step 4: Data Validation

1. **Validate User Inputs:**
   - Ensure that the amount entered is a valid number and not negative.
   - Validate the date format (e.g., YYYY-MM-DD) and check if the date is valid.

   ```python
   def validate_date(date_str):
       # Your code to validate the date string

   def validate_amount(amount_str):
       # Your code to validate the amount
   ```

### Assignment Deliverables:

- Update your Python script with the new features and ensure all previous functionalities are intact.
- Test all new features thoroughly to ensure they work as expected.
- Update your `README.md` file to include descriptions of the new features and instructions on how to use them.

This assignment is designed to solidify your Python skills, introduce more advanced programming concepts, and provide a tangible project you can showcase. Good luck!

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)
