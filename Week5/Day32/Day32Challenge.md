# Control Flow - If Statements in Python

Welcome to Day 4 of our Python exploration! Today, we'll delve into control flow, specifically focusing on conditional statements and if statements.

## Conditional Statements

Conditional statements allow your program to make decisions based on conditions. The most basic form is the **if statement**.

```python
# Basic if statement
if condition:
    # Code to execute if the condition is true
    print("Condition is true.")
```

## If Statements in Python

In Python, the structure of an if statement is clear and concise. It uses indentation to define the code block that should be executed if the condition is true.

```python
# Example of an if statement
age = 25

if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```

### If-Elif-Else Statements

Multiple conditions can be checked using the if-elif-else structure.

```python
# Example of an if-elif-else statement
temperature = 25

if temperature > 30:
    print("It's hot outside.")
elif 20 <= temperature <= 30:
    print("It's a pleasant day.")
else:
    print("It's cool outside.")
```

## Exercise

Create a Python script that utilizes if statements:

1. Ask the user to input their age.
2. If the age is less than 18, print a message indicating they are a minor.
3. If the age is between 18 and 65 (inclusive), print a message indicating they are an adult.
4. If the age is greater than 65, print a message indicating they are a senior citizen.
5. Ask the user to input a number and check if it's positive, negative, or zero. Print the result.

Run the script in your VSCode environment, input different values, and observe how the program responds to different conditions. Understanding control flow is crucial for creating dynamic and responsive programs. Happy coding! 🚀 #Day4ofPython #100DaysofCodingChallenge #PythonIfStatements