# Control Flow - Loops in Python

Welcome to Day 5 of our Python journey! Today, we'll explore control flow with a focus on loops - an essential part of programming for repetitive tasks.

## For Loops

A **for loop** is used to iterate over a sequence (such as a list, tuple, or string) and execute a block of code for each element.

```python
# Example of a for loop
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

### Range Function

The `range()` function is often used with for loops to generate a sequence of numbers.

```python
# Using range() in a for loop
for number in range(5):
    print(number)
```

## While Loops

A **while loop** continues to execute a block of code as long as a condition is true.

```python
# Example of a while loop
count = 0

while count < 5:
    print(count)
    count += 1
```

### Break and Continue Statements

- The `break` statement terminates the loop prematurely.
- The `continue` statement skips the rest of the code inside the loop for the current iteration.

```python
# Example using break and continue
for number in range(10):
    if number == 5:
        break
    elif number % 2 == 0:
        continue
    print(number)
```

## Exercise

Create a Python script that involves both for and while loops:

1. Use a for loop to print the square of each number from 1 to 5.
2. Use a while loop to print the cube of each number from 1 to 3.
3. Create a list of your favorite books and use a for loop to print each book's title.
4. Use a while loop to continuously ask the user to enter a number until they enter 0. Print the sum of all entered numbers.

Run the script in your VSCode environment, observe the output, and experiment with different loop scenarios. Loops are powerful tools for automating repetitive tasks in your programs. Happy coding! 🚀 #Day5ofPython #100DaysofCodingChallenge #PythonLoops