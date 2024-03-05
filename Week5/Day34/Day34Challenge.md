# Functions and Dictionaries in Python

Welcome to Days 6 of our Python journey! Today, we'll combine the power of functions with the versatility of dictionaries.

## Defining Functions

In Python, functions are defined using the `def` keyword, allowing you to organize and reuse code.

```python
# Example of a function with parameters and return value
def greet(name):
    return f"Hello, {name}!"
```

## Parameters and Return Values

Parameters allow functions to accept input, and return values enable them to produce output.

```python
# Function to add two numbers and return the result
def add_numbers(a, b):
    return a + b
```

## Dictionaries in Python

A **dictionary** is an unordered collection of items. Each item has a key-value pair, providing a way to store and retrieve data efficiently.

```python
# Example of a dictionary
person = {
    "name": "Alice",
    "age": 30,
    "city": "Wonderland"
}
```

### Accessing Dictionary Elements

You can access values in a dictionary using their keys.

```python
# Accessing values in a dictionary
name = person["name"]
age = person["age"]
```

### Adding and Modifying Dictionary Items

```python
# Adding a new item
person["occupation"] = "Adventurer"

# Modifying an existing item
person["age"] = 31
```

## Exercise

Let's create a Python script that combines functions and dictionaries:

1. Define a function called `calculate_area` that takes the dimensions (length and width) of a rectangle as parameters and returns its area.
2. Use the `calculate_area` function to find the area of a rectangle with dimensions 8x5 and print the result.
3. Create a dictionary representing a person's information (name, age, city).
4. Define a function called `print_person_info` that takes a person dictionary as a parameter and prints their information in a formatted manner.
5. Use the `print_person_info` function to display the information of the person created in step 3.

Run the script in your VSCode environment, observe the output, and enjoy the seamless integration of functions and dictionaries in Python. Happy coding! 🚀 #Day6and7ofPython #100DaysofCodingChallenge #PythonFunctions #PythonDictionaries