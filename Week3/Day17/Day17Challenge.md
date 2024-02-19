## Day 17: Introduction to Functions in JavaScript

### Introduction to Functions

Functions in JavaScript are blocks of code designed to perform a particular task, making it a cornerstone of not just JavaScript, but of programming in general. When you define a function, you write the steps needed to achieve a certain task. Calling the function will execute those steps. The beauty of functions lies in their reusability and the ability to define the task once and use it multiple times.

### Function Declarations vs. Expressions

**Function Declarations:**
These are the more traditional way to define a function. The syntax looks like this:

```javascript
function functionName(parameters) {
  // Code to be executed
}
```

Declared functions are hoisted, meaning they can be called before they are defined in the code. This allows for more flexibility in code organization.

**Example:**

```javascript
function sayHello() {
  console.log('Hello!');
}
sayHello(); // Calls the function, resulting in "Hello!" being printed to the console.
```

**Function Expressions:**
Function expressions allow you to create anonymous functions (functions without a name) that are not hoisted. This means you cannot call them before they are defined in the script.

```javascript
const functionName = function(parameters) {
  // Code to be executed
};
```

**Example:**

```javascript
const sayGoodbye = function() {
  console.log('Goodbye!');
};
sayGoodbye(); // Calls the function, outputting "Goodbye!" to the console.
```

### Parameters and Return Statements

**Parameters** are the names listed in the function definition, while **arguments** are the real values received by the function when it is invoked. Inside the function, the arguments (the parameters) behave as local variables.

```javascript
function greet(name) {
  console.log('Hello ' + name + '!');
}
greet('Alice'); // Outputs: Hello Alice!
```

A **Return Statement** ends function execution and specifies a value to be returned to the function caller.

```javascript
function sum(a, b) {
  return a + b;
}
console.log(sum(5, 3)); // Outputs: 8
```

### Real-Life Example

Think of a function as a coffee machine. You provide inputs (coffee beans, water), and it performs a task (brewing coffee) to produce an output (your coffee). Parameters are like the specific amount and type of coffee beans and water you put in, and the return value is the coffee that comes out, which you can then drink or pour into different cups.

### Assignment: Simple Calculator

Create a simple calculator that can add, subtract, multiply, and divide two numbers. Use function declarations for each operation and allow the user to input two numbers and the operation they wish to perform.

1. Declare 3 variables, input1,input2 and operation.
2. Declare the functions for add, subtract, multiply and divide
3. Based on the operation, return the output of the result

<center><img src="https://github.com/adithyasai/100daysofcodingchallenge/blob/week1/images/week3_ss3.png" width="800" height="400"></center>

<center><img src="https://github.com/adithyasai/100daysofcodingchallenge/blob/week1/images/week3_ss4.png" width="800" height="400"></center>

### Assignment2: Simple Task Management

Create a simple project management tool. It will allow you to add tasks, complete tasks, and display the status of tasks.

**Requirements:**

1. Create functions to add a task and display tasks.
2. Use an array to store tasks.

<center><img src="https://github.com/adithyasai/100daysofcodingchallenge/blob/week1/images/week3_ss5.png" width="800" height="400"></center>


### LinkedIn Post for Achievement
Day 17/100 - Diving deep into the world of JavaScript functions! 🚀 Today, I explored the essence of function declarations vs. expressions, unraveled the mysteries of parameters, and mastered return statements. #100DaysofCodingChallenge #codewithaadi 📚

**Fantastic job on completing this assignment! Collaboration makes coding even more exciting. Keep up the great work!** 🚀💻

## Follow us:
- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)