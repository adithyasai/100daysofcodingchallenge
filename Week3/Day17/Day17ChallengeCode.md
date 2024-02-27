### Assignment1: Simple Calculator
```javascript
function add(a, b) {
    return a + b;
  }
  
  function subtract(a, b) {
    return a - b;
  }
  
  function multiply(a, b) {
    return a * b;
  }
  
  function divide(a, b) {
    return a / b;
  }
  
  // Example usage:
  const num1 = 76;
  const num2 = 23;
  const operation = "subtract";
  
  let result;
  switch (operation) {
    case 'add':
      result = add(num1, num2);
      break;
    case 'subtract':
      result = subtract(num1, num2);
      break;
    case 'multiply':
      result = multiply(num1, num2);
      break;
    case 'divide':
      result = divide(num1, num2);
      break;
    default:
      console.log('Invalid operation');
      break;
  }
  
  console.log(`The result is ${result}`);
  ```

### Assignment2 : Simple Task Management
```javascript
let tasks = [];

function addTask(taskName) {
    tasks.push(taskName);
}

function displayTasks() {
    for (let i = 0; i < tasks.length; i++) {
        console.log(`${tasks[i]}`);
    }

}

// Simulating user interaction:
addTask('Learn JavaScript');
addTask('Practice exercises');
displayTasks();
```