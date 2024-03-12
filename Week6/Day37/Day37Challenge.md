## Day 37: Exception Handling in Python - Dive Deeper

### Introduction to Exception Handling

Exception handling is a critical concept in Python and programming in general, allowing for the management of unexpected errors in a graceful manner. It ensures that the flow of the program isn't abruptly disrupted and provides a mechanism for resolving runtime errors.

### Types of Exceptions in Python

Python categorizes errors into two major types: syntax errors and exceptions. Syntax errors occur when the parser detects an incorrect statement. Exceptions, however, occur during the execution of a correct syntax script, due to incorrect operations, like dividing by zero.

### The try-except Block

The primary mechanism provided by Python for handling exceptions is the `try-except` block. The code that could potentially cause an error is placed inside the `try` block, and the handling of the exception is implemented in the `except` block.

```python
try:
    # Code that might lead to an exception
    risky_operation = 1 / 0
except ZeroDivisionError:
    # Handling the exception
    print("Attempted to divide by zero.")
```

When catching exceptions, you can access the exception object itself, which might give you detailed information about what went wrong.

```python
try:
    # Code that might lead to an exception
    risky_operation = 1 / 0
except ZeroDivisionError as e:
    # Accessing exception information
    print(f"Exception occurred: {e}")
```

### Catching Multiple Exceptions

A single `try` block can handle multiple exceptions. This can be done by specifying multiple `except` blocks. Each `except` block will handle a specific type of exception.

```python
try:
    # Code that might lead to multiple types of exceptions
    operation = 1 / undefined_variable
except ZeroDivisionError:
    print("Attempted to divide by zero.")
except NameError:
    print("Used a variable that is not defined.")
```

### The else Clause

The `else` clause is executed if no exceptions were raised in the `try` block. It's a good place to put code that should only run if the `try` block was successful.

```python
try:
    # Code that might lead to an exception
    safe_operation = 1 / 2
except ZeroDivisionError:
    print("Attempted to divide by zero.")
else:
    print("Operation was successful.")
```

### The finally Block

The `finally` block, if present, will always be executed, regardless of whether an exception was caught or not. It's typically used for clean-up actions, such as closing files or releasing resources.

```python
try:
    # Attempting to open a file
    file = open("example.txt", "r")
    file_content = file.read()
except FileNotFoundError:
    print("The file does not exist.")
finally:
    # This block will run no matter what
    file.close()
    print("File closed.")
```

### Raising Exceptions

You can also raise exceptions in your code using the `raise` statement. This is useful when you need to enforce certain conditions or handle errors in a specific way.

```python
def set_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative.")
    print(f"Age set to {age}")

try:
    set_age(-1)
except ValueError as e:
    print(e)
```

### Real-Life Example: Validating User Input

Imagine a function that prompts the user for their age and checks if it's a valid positive integer. If the input is invalid, the function raises an exception.

```python
def get_user_age():
    try:
        age = int(input("Enter your age: "))
        if age < 0:
            raise ValueError("Age cannot be negative.")
    except ValueError as e:
        print(f"Invalid input: {e}")
    else:
        print(f"Your age is {age}")

get_user_age()
```

For Day 9's assignment on Exception Handling in Python, we'll create a simple program that performs division operations. This program will request two numbers from the user and divide the first number by the second. The assessment will focus on handling potential exceptions that could occur during this operation, such as division by zero or non-numeric input.

### Assignment: Safe Division Program

**Objective:** Write a Python program that safely performs division operations. The program should prompt the user for two numbers and then divide the first by the second. It should handle exceptions for division by zero and non-numeric inputs, displaying user-friendly error messages.

**Requirements:**

1. Prompt the user to input two numbers.
2. Perform the division operation in a try-except block.
3. Handle `ZeroDivisionError` for cases where the second number is zero.
4. Handle `ValueError` for non-numeric inputs.
5. Display the result of the division if successful.
6. Provide a user-friendly error message for each exception.
7. Allow the user to exit or perform another calculation.

### LinkedIn Post for Achievement

"Day 37 of #100DaysOfCodingChallenge: Tackled Exception Handling in Python! Learned to gracefully manage unexpected errors, ensuring my programs are robust and user-friendly. From try-except blocks to raising custom exceptions
#Day37 #100DaysOfCodingChallenge #Python"

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)
