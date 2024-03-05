# Lists and Tuples in Python

Welcome to Day 3 of our Python journey! Today, we'll explore two essential data structures in Python: Lists and Tuples. These structures allow you to store and manipulate collections of items.

## Lists

A **list** is a mutable, ordered collection of items. It can contain elements of different data types, and you can modify its content.

```python
# Creating a list
fruits = ["apple", "banana", "cherry"]

# Accessing elements
first_fruit = fruits[0]
```

### List Operations

```python
# Adding elements to the end of the list
fruits.append("orange")

# Inserting an element at a specific index
fruits.insert(1, "grape")

# Removing an element by value
fruits.remove("banana")

# Removing an element by index
removed_fruit = fruits.pop(2)

# Checking if an element is in the list
is_apple_in_list = "apple" in fruits
```

## Tuples

A **tuple** is an immutable, ordered collection of items. Once you create a tuple, you cannot change its content.

```python
# Creating a tuple
colors = ("red", "green", "blue")

# Accessing elements
first_color = colors[0]
```

### Tuple Operations

```python
# Concatenating tuples
new_colors = colors + ("yellow", "orange")

# Repetition
repeated_colors = colors * 2

# Checking if an element is in the tuple
is_red_in_tuple = "red" in colors
```

## Exercise

Create a Python script that involves both lists and tuples:

1. Create a list of your favorite movies.
2. Add a new movie to the list.
3. Create a tuple with the release years of the movies.
4. Print the third movie in your list and its release year.
5. Check if a specific movie is in your list.
6. Concatenate your list of movies with a friend's list and print the combined list.

Run the script in your VSCode environment and observe the results. Lists and tuples are powerful tools for managing collections of data in Python. Happy coding! 🚀 #Day3ofPython #100DaysofCodingChallenge #PythonListsAndTuples