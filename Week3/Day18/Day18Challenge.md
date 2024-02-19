## Day 18: Diving Deeper into JavaScript Functions

### Scope and Lexical Scope

**Scope** in JavaScript determines the accessibility of variables and functions at various parts of your code. There are two main types: global scope and local (function/lexical) scope.

- **Global Scope:** Variables defined outside any function or block have a global scope, meaning they can be accessed and altered from anywhere in the code.

```javascript
let globalVar = 'I am global';

function checkScope() {
  console.log(globalVar); // Accessible here
}

checkScope(); // Output: I am global
```

- **Local (Lexical) Scope:** Variables declared within a function are locally scoped to that function and cannot be accessed from outside.

```javascript
function greet() {
  let name = 'Alice';
  console.log(`Hello, ${name}!`); // Accessible here
}

greet(); // Output: Hello, Alice!
console.log(name); // Error: name is not defined
```

### Closures

A **closure** is a function that has access to the parent scope, even after the parent function has closed. This is a powerful feature in JavaScript that allows for data encapsulation and the creation of private variables.

**Example:**

```javascript
function makeGreeting() {
  let name = 'Bob';
  return function() {
    console.log(`Hello, ${name}!`);
  };
}

let greetBob = makeGreeting();
greetBob(); // Output: Hello, Bob!
```

**Practical Use Cases:**
- Creating private variables
- Writing function factories
- Handling events in web pages without leaking memory

### Arrow Functions

Arrow functions provide a concise syntax for writing function expressions. They are particularly useful for short functions and when using functions as arguments.

```javascript
const add = (a, b) => a + b;

console.log(add(5, 3)); // Output: 8
```

Arrow functions do not have their own `this`, `arguments`, `super`, or `new.target` bindings. These functions are best suited for non-method functions.

### Assignment: Personal Finance Tracker

Create a simple personal finance tracker that allows you to track income and expenses and provides a balance summary.

**Requirements:**

1. Use closures to create private variables for income and expenses.
2. Implement functions to add income, add an expense, and calculate the balance using these closures.
3. Use arrow functions for simple calculations.

<center><img src="https://github.com/adithyasai/100daysofcodingchallenge/blob/main/images/week3_ss6.png" width="800" height="400"></center>

In this project, you'll apply closures to keep track of income and expenses, providing a neat way to manage personal finances without exposing the actual income and expense variables.

### LinkedIn Post for Achievement

"Day 18 of #100DaysOfCoding was enlightening! 🌟 Mastered JavaScript closures, delved into scope, and embraced arrow functions by building a personal finance tracker. Every day brings new insights and skills. #100DaysofCodingChallenge #codewithaadi

## Follow us:
- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)