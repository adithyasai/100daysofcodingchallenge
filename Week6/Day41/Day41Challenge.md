# Day 41 Mini-Project: Python-Based Command-Line Personal Expense Tracker

For Day 41, let's create a Personal Expense Tracker that operates entirely from the command line. This project will strengthen your Python skills, particularly in handling data structures, reading from and writing to files, and building interactive command-line interfaces.

## Project Overview

The Personal Expense Tracker will allow users to add, view, and delete their expenses through the command line. Each expense record will include details like the amount, description, and date.

### Features:

- **Add Expense:** Users can input the amount, description, and date of an expense.
- **View Expenses:** Display a list of recorded expenses.
- **Delete Expense:** Users can remove an expense entry.

## Tools and Technologies

- **Python:** All functionality will be implemented using Python, utilizing built-in libraries.
- **JSON:** Expense records will be stored in a simple JSON file, enabling persistence between sessions.

## Step-by-Step Guide

### Step 1: Project Setup

1. **Initialize Your Project:**
   - Create a new directory for your project, e.g., `expense_tracker`.
   - Inside this directory, create a Python script for the tracker, e.g., `tracker.py`.

### Step 2: Designing the Data Structure

1. **Define the Expense Model:**
   - Decide on the structure of an expense record. A simple dictionary can suffice, e.g., `{'amount': 10.50, 'description': 'Coffee', 'date': '2023-03-12'}`.
   
2. **Initialize a JSON File:**
   - Create a JSON file, e.g., `expenses.json`, to store the expense records. Initialize it with an empty list `[]`.

### Step 3: Implementing Core Features

1. **Adding an Expense:**
   - Implement a function to add a new expense. This function should prompt the user for the amount, description, and date, then append the new expense to the list and save it to the JSON file.

   ```python
   import json

   def add_expense():
       amount = float(input("Enter expense amount: "))
       description = input("Enter expense description: ")
       date = input("Enter date of expense (YYYY-MM-DD): ")

       new_expense = {'amount': amount, 'description': description, 'date': date}

       with open('expenses.json', 'r+') as file:
           expenses = json.load(file)
           expenses.append(new_expense)
           file.seek(0)
           json.dump(expenses, file)
   ```

2. **Viewing Expenses:**
   - Create a function to read and display all expenses from the JSON file.

   ```python
   def view_expenses():
       with open('expenses.json', 'r') as file:
           expenses = json.load(file)
           for expense in expenses:
               print(f"{expense['date']}: {expense['description']} - ${expense['amount']}")
   ```

3. **Deleting an Expense:**
   - Implement a function to delete an expense by its index in the list. You may want to first display expenses with their indices.

   ```python
   def delete_expense():
       view_expenses()
       index = int(input("Enter the index of the expense to delete: "))
       
       with open('expenses.json', 'r+') as file:
           expenses = json.load(file)
           if 0 <= index < len(expenses):
               expenses.pop(index)
               file.seek(0)
               file.truncate()
               json.dump(expenses, file)
           else:
               print("Invalid index.")
   ```

### Step 4: Building the Command-Line Interface

1. **Implement a Simple CLI:**
   - Use a while loop to continuously prompt the user for actions (add, view, delete, or exit).

   ```python
   def main():
       while True:
           action = input("Choose an action (add, view, delete, exit): ").lower()
           if action == 'add':
               add_expense()
           elif action == 'view':
               view_expenses()
           elif action == 'delete':
               delete_expense()
           elif action == 'exit':
               break
           else:
               print("Invalid action.")

   if __name__ == "__main__":
       main()
   ```

### Step 5: Testing and Refinement

1. **Run Your Tracker:**
   - Execute `tracker.py` and test all functionalities: adding, viewing, and deleting expenses.
   - Ensure data persists correctly across sessions by checking `expenses.json`.

2. **Refine and Comment:**
   - Go through your code, refactor as needed for clarity and efficiency, and add comments explaining key sections.

By following these steps, you will have developed a functional command-line Personal Expense Tracker. This project demonstrates your ability to manipulate data structures, interact with files, and build practical Python applications.

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)
