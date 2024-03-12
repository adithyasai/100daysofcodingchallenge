## Day 39: Exploring Python Libraries

### Introduction to Python Libraries

Python libraries are collections of pre-compiled routines and functions that programmers can use to optimize and enhance their Python projects. These libraries extend Python's capabilities, allowing for more efficient development in areas such as data analysis, machine learning, web development, and more.

### Popular Python Libraries

1. **NumPy:** Provides support for large, multi-dimensional arrays and matrices, along with a collection of mathematical functions to operate on these arrays.
2. **Pandas:** Offers data structures and operations for manipulating numerical tables and time series, making data manipulation and analysis more accessible.
3. **Matplotlib:** A plotting library for creating static, interactive, and animated visualizations in Python.
4. **Requests:** Allows you to send HTTP/1.1 requests easily, adding essential web content downloading capabilities to your Python projects.

### Using Python Libraries

To use a library in Python, you first need to ensure it's installed. You can typically install Python libraries using pip, Python's package installer. Once installed, you can import the library or specific functions from it into your Python scripts.

```python
# Installing a library using pip (example: NumPy)
!pip install numpy

# Importing a library
import numpy as np

# Using a function from the library
array = np.array([1, 2, 3, 4, 5])
```

### NumPy Basics

NumPy is fundamental for scientific computing with Python. It provides an efficient interface to store and operate on dense data buffers.

```python
import numpy as np

# Creating an array
arr = np.array([1, 2, 3, 4, 5])

# Performing operations
print("Original Array:", arr)
print("Array after adding 5:", arr + 5)
```

### Pandas for Data Manipulation

Pandas is a fast, powerful, flexible, and easy-to-use open-source data analysis and manipulation tool built on top of Python.

```python
import pandas as pd

# Creating a DataFrame
data = {'Name': ['John', 'Anna', 'Peter', 'Linda'],
        'Age': [28, 34, 29, 32]}
df = pd.DataFrame(data)

# Display the DataFrame
print(df)
```

### Visualization with Matplotlib

Matplotlib is a comprehensive library for creating static, animated, and interactive visualizations in Python.

```python
import matplotlib.pyplot as plt

# Data for plotting
t = np.arange(0.0, 2.0, 0.01)
s = 1 + np.sin(2 * np.pi * t)

# Plotting
plt.figure()
plt.plot(t, s)
plt.title('Simple plot')
plt.xlabel('time (s)')
plt.ylabel('value')
plt.grid(True)
plt.show()
```

### Accessing Web Content with Requests

The Requests library is the de facto standard for making HTTP requests in Python, thanks to its simplicity and ease of use.

```python
import requests

# Making a GET request
response = requests.get('https://api.github.com')

# Display the status code
print("Status Code:", response.status_code)

# Display a portion of the response content
print("Response Content:", response.content[:100])
```

For a beginner-friendly assignment, let's work with a simple dataset that lists fruits and their corresponding prices and quantities. This assignment will guide you through loading the dataset, performing basic manipulations, and creating a simple visualization. We'll use Python's Pandas and Matplotlib libraries, ensuring you get hands-on experience with these essential data analysis tools.

Follow the walk through to understand simple Data Analysis

### Code Walk Through: Fruit Market Analysis

#### Objective
Analyze a dataset containing information about fruits, their prices, and available quantities in a fruit market. Perform data manipulations using Pandas and visualize the data with Matplotlib.

#### Dataset
For simplicity, we'll create a small dataset using Python's list and dictionary structures. This dataset will then be converted into a Pandas DataFrame.

#### Step 1: Setting Up Your Environment
Ensure you have Python, Pandas, and Matplotlib installed in your environment. You can install Pandas and Matplotlib using pip if you haven't already:

```bash
pip install pandas matplotlib
```

#### Step 2: Creating the Dataset
Start by creating a simple dataset. In a Python script or a Jupyter Notebook, initialize the dataset as follows:

```python
import pandas as pd

# Data
data = {
    "Fruit": ["Apples", "Oranges", "Bananas", "Strawberries", "Grapes"],
    "Price": [1.5, 2.0, 0.8, 3.0, 2.5],
    "Quantity": [20, 33, 45, 12, 40]
}

# Creating a DataFrame
df = pd.DataFrame(data)
```

#### Step 3: Basic Data Manipulation
Perform some basic manipulations on your DataFrame. For example, you can calculate the total value (price * quantity) for each fruit.

```python
# Calculating total value
df['Total Value'] = df['Price'] * df['Quantity']
print(df)
```

#### Step 4: Simple Data Analysis
Analyze the data to find which fruit has the highest total value in the market.

```python
# Finding the fruit with the highest total value
max_value_fruit = df.loc[df['Total Value'].idxmax()]
print(f"The fruit with the highest total value is: {max_value_fruit['Fruit']}")
```

#### Step 5: Data Visualization
Use Matplotlib to create a bar chart showing the quantity available for each fruit.

```python
import matplotlib.pyplot as plt

# Setting up the plot
plt.figure(figsize=(8, 4))
plt.bar(df['Fruit'], df['Quantity'], color='skyblue')

# Adding titles and labels
plt.title('Quantity of Fruits in the Market')
plt.xlabel('Fruit')
plt.ylabel('Quantity')

# Displaying the plot
plt.show()
```

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)
