## Day 22: Understanding the DOM, Selecting and Manipulating DOM Elements, Events and Event Handling in JavaScript

### Introduction to the DOM

The Document Object Model (DOM) is a programming interface for web documents. It represents the structure of a document as a tree of objects, where each object corresponds to a part of the document, such as elements, attributes, and text.

### Understanding the DOM Tree

The DOM tree is a hierarchical representation of the document's structure. Elements, attributes, and text are nodes in this tree. JavaScript allows us to manipulate the DOM dynamically, enabling us to update and change the content and structure of a web page in real-time.

### Selecting DOM Elements

Selecting DOM elements is a crucial part of working with the DOM. JavaScript provides various methods to select elements based on their tag name, class, ID, or other attributes.

```javascript
// Selecting by ID
let elementById = document.getElementById("myElementId");

// Selecting by class name
let elementsByClass = document.getElementsByClassName("myClassName");

// Selecting by tag name
let elementsByTag = document.getElementsByTagName("div");

// Selecting by CSS selector
let elementBySelector = document.querySelector(".myClass");
```

### Manipulating DOM Elements

Once you've selected elements, you can manipulate them by changing their content, attributes, or even adding and removing them from the document.

```javascript
// Changing content
elementById.innerHTML = "New Content";

// Changing attributes
elementById.setAttribute("src", "newImage.jpg");

// Creating new elements
let newElement = document.createElement("p");
newElement.innerHTML = "This is a new paragraph.";
document.body.appendChild(newElement);

// Removing elements
document.body.removeChild(elementById);
```

### Events and Event Handling

Events are actions or occurrences that happen in the browser, such as a button click or a keypress. Event handling allows you to define JavaScript code that should run when a specific event occurs.

```javascript
// Adding an event listener
elementById.addEventListener("click", function () {
  console.log("Button clicked!");
});

// Event object
elementById.addEventListener("mouseover", function (event) {
  console.log(`Mouse over at coordinates: ${event.clientX}, ${event.clientY}`);
});

// Removing an event listener
function handleClick() {
  console.log("Button clicked!");
}

elementById.addEventListener("click", handleClick);
elementById.removeEventListener("click", handleClick);
```

### Real-Life Example: Interactive Form Validation

Let's apply these concepts to create a simple form with interactive validation.

```html
<form id="myForm">
  <label for="username">Username:</label>
  <input type="text" id="username" required />
  <span id="usernameError" style="color: red;"></span>

  <label for="password">Password:</label>
  <input type="password" id="password" required />
  <span id="passwordError" style="color: red;"></span>

  <button type="submit">Submit</button>
</form>
```

```javascript
document.getElementById("myForm").addEventListener("submit", function (event) {
  let username = document.getElementById("username").value;
  let password = document.getElementById("password").value;

  if (username.length < 5) {
    document.getElementById("usernameError").innerHTML =
      "Username must be at least 5 characters";
    event.preventDefault(); // Prevent form submission
  } else {
    document.getElementById("usernameError").innerHTML = "";
  }

  if (password.length < 8) {
    document.getElementById("passwordError").innerHTML =
      "Password must be at least 8 characters";
    event.preventDefault(); // Prevent form submission
  } else {
    document.getElementById("passwordError").innerHTML = "";
  }
});
```

### Assignment: Build a To-Do List with Event Handling

Extend your coding skills by building a to-do list application. Utilize DOM manipulation and event handling to add tasks, mark them as completed, and remove them from the list.

**Requirements:**

1. Create an HTML structure for the to-do list with input fields and buttons.
2. Use JavaScript to dynamically add tasks to the list when the user submits the form.
3. Implement event handling to mark tasks as completed or remove them from the list when the user interacts with them.

<center><img src="https://github.com/adithyasai/100daysofcodingchallenge/blob/main/images/week3_ss9.png" width="800" height="400"></center>

In this assignment, you'll dive deeper into the DOM, enhancing your understanding of JavaScript's capabilities in creating interactive and dynamic web applications. Good luck, and happy coding!

### LinkedIn Post for Achievement

"Day 22 on my coding journey, and I'm delving into the wonders of the DOM in JavaScript! 🌐 From selecting and manipulating elements to mastering events and event handling, I'm building interactive web applications with ease. 💻✨ #Day22 #100DaysOfCoding #DOM #JavaScriptMagic #WebDevJourney #codewithaadi

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)

---
