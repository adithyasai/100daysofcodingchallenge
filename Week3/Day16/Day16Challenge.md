### Installing Node.js

Node.js is a runtime environment that allows you to run JavaScript on the server side. To install Node.js, follow these steps:

1. **Download Node.js:**
   - Go to the [official Node.js website](https://nodejs.org/).
   - You'll see two versions available for download: LTS (Long Term Support) and Current. For most users, the LTS version is recommended because it's more stable.

2. **Installation:**
   - Run the downloaded installer, which is an executable `.exe` file on Windows or a `.pkg` file on macOS.
   - Follow the installation prompts, accepting the license agreement and default settings unless you need to customize the install paths.

3. **Verify Installation:**
   - Open your command line interface (CLI), which is Command Prompt on Windows or Terminal on macOS and Linux.
   - Type `node -v` and press Enter. This should print the version of Node.js that was installed, confirming the installation was successful.
   - Additionally, check npm (Node Package Manager) is installed by typing `npm -v`.

### Running a JavaScript File in VS Code

Visual Studio Code (VS Code) is a powerful and popular code editor for developers. To run a JavaScript file in VS Code:

1. **Open VS Code:**
   - Launch VS Code. If you haven't already installed it, download it from the [official VS Code website](https://code.visualstudio.com/) and install it following the prompts.

2. **Create a JavaScript File:**
   - You can create a new file by clicking on the 'New File' icon in the Explorer panel or by pressing `Ctrl + N` (or `Cmd + N` on macOS).
   - Save the file with a `.js` extension, like `script.js`, by pressing `Ctrl + S` (or `Cmd + S` on macOS).

3. **Write Some JavaScript Code:**
   - Type your JavaScript code into the file. For example:
     ```javascript
     console.log('Hello, Node.js!');
     ```

4. **Open the Integrated Terminal:**
   - You can open the terminal in VS Code by pressing `` Ctrl + ` `` (the backtick key), or by going to the top menu and selecting `Terminal > New Terminal`.

5. **Run the JavaScript File:**
   - In the terminal, type `node script.js` (replace `script.js` with the path to your JavaScript file if it's located in a different folder).
   - Press Enter, and you should see the output of your JavaScript code in the terminal.

By installing Node.js and using VS Code's integrated terminal, you have the tools to write and execute JavaScript code efficiently on your computer.

## Control Flow: Conditional Statements (if, else if, else)

Conditional statements control the flow of execution based on conditions. The syntax for a simple if statement is as follows:

- The `if` statement is the fundamental control statement that allows JavaScript to make decisions and execute statements conditionally.
- It is used when you want to execute a block of code only if a particular condition is true.

```javascript
if (condition) {
  // code to execute if the condition is true
}
```

For multiple conditions, else if and else can be used:
- These statements are used in conjunction with `if` to create a chain of conditions.
- `else if` is used when you have multiple conditions that need to be tested in sequence.
- `else` is used as a default when none of the preceding `if` or `else if` conditions are met.
- **Example Use Case:** Displaying different messages based on a student's grade (A, B, C, or F).

```javascript
if (condition1) {
  // code to execute if condition1 is true
} else if (condition2) {
  // code to execute if condition2 is true
} else {
  // code to execute if none of the above conditions are true
}
```

**Example:**
```javascript
let weather = 'rainy';

if (weather === 'sunny') {
  console.log('Wear sunglasses!');
} else if (weather === 'rainy') {
  console.log('Don't forget an umbrella!');
} else {
  console.log('Check the weather forecast.');
}
// Output: Don't forget an umbrella!
```

Choosing what to wear based on the weather.

## Control Flow: Loops (for, while)

Loops are used to execute a block of code multiple times.

**For Loop Syntax:**
- The `for` loop provides a concise way of writing a loop structure when the number of iterations is known before entering the loop.
- It's typically used for iterating over arrays or executing a block of code a specific number of times.

```javascript
for (initialization; condition; final expression) {
  // code to execute on each iteration
}
```

**Example:**
```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);
}
// Output: 0 1 2 3 4
```

**While Loop Syntax:**

- The `while` loop is used to repeat a block of code an unknown number of times until a condition changes to false.
- It's best used when the number of iterations is not known beforehand, and the loop needs to continue as long as a certain condition is true.

```javascript
while (condition) {
  // code to execute as long as the condition is true
}
```

**Example:**
```javascript
let i = 0;
while (i < 5) {
  console.log(i);
  i++;
}
// Output: 0 1 2 3 4
```

**Real Life Example:**
Printing each page in a document until all pages are printed.

## Arrays and Basic Array Methods

Arrays store multiple values in a single variable.
Introducing the concept of arrays can be likened to explaining how to organize a collection of items in real life. Here’s a way to contextualize arrays:

### Introduction to Arrays

Imagine you have a bookshelf. On this bookshelf, you want to organize your collection of books so that you can access them easily. Each slot on the shelf can hold one book. Now, instead of having to remember where each book is, you just need to remember the order in which they’re placed. The first slot holds the first book, the second slot holds the second book, and so on. This is essentially what an array does in programming.

An array is a structured way to organize and manipulate a collection of data. It allows you to store multiple values in a single, cohesive unit. Think of it as a list of items, where each item can be accessed by its position or index in that list.

### Why Use Arrays?

Arrays are incredibly useful because:

- They store multiple items under a single variable name, making your code neater and more manageable.
- You can loop through an array to perform operations on each element.
- They offer a suite of built-in methods that allow for complex operations like adding and removing items, searching for items, and sorting the array in order.

### JavaScript Array Example

```javascript
let fruits = ['Apple', 'Banana', 'Cherry'];
console.log(fruits[0]); // Accesses the first element: Apple
```

In this example, `fruits` is an array that stores three strings. Each string is an item in the array. The items are zero-indexed, which means the first item is at index `0`, the second item is at index `1`, and so on.

Arrays in programming are powerful because they're not limited to storing just strings. You can store numbers, booleans, and even other arrays. This versatility makes arrays a fundamental aspect of managing collections of data in programming.

**Example:**
```javascript
let fruits = ['Apple', 'Banana', 'Cherry'];
console.log(fruits[1]); // Accessing the second element
// Output: Banana
```

Basic array methods:

- `.push()` adds an item to the end of an array.
- `.pop()` removes the last item from an array.
- `.shift()` removes the first item from an array.
- `.unshift()` adds an item to the beginning of an array.

**Example:**
```javascript
fruits.push('Date');
console.log(fruits); // Output: ['Apple', 'Banana', 'Cherry', 'Date']
```

**Real Life Example:**
Managing a to-do list where you can add or remove tasks.

## Assignment: Simple Project

**Task:** Create a script that manages a to-do list.

1. Initialize an array to store tasks for the week.
2. Use a for loop to simulate each day of the week.
3. On Monday, you will start the JavaScript Course
4. Every alternate day, you revise the previous week's concepts.
5. Print the tasks for the week (use any loop)

<center><img src="https://github.com/adithyasai/100daysofcodingchallenge/blob/week1/images/week3_ss2.png" width="800" height="400"></center>

### LinkedIn Post for Achievement
Day 16/100 - Another productive day in my coding journey! 🚀 I've just leveled up my JavaScript skills by mastering arrays and control flow with loops and conditional statements.  #Day15ofJavaScript #100DaysofCodingChallenge #codewithaadi

**Fantastic job on completing this assignment! Collaboration makes coding even more exciting. Keep up the great work!** 🚀💻

## Follow us:
- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)