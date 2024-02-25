Certainly! Here's the content for Day 23 in Markdown format:

````markdown
# Day 23: Advanced DOM Manipulation, Event Delegation, Practical Examples, and Mini Projects in JavaScript

## Advanced DOM Manipulation

As we delve deeper into the world of web development, advanced DOM manipulation becomes essential. This involves manipulating the DOM with more complexity, handling dynamic changes, and optimizing performance.

### Modifying Styles

```javascript
// Change element style
element.style.color = "red";

// Toggle class
element.classList.toggle("active");
```
````

### Traversing the DOM

```javascript
// Navigate to parent, child, or sibling elements
let parent = element.parentNode;
let firstChild = element.firstChild;
let nextSibling = element.nextSibling;
```

### Working with Attributes

```javascript
// Get attribute value
let srcValue = image.getAttribute("src");

// Set attribute value
image.setAttribute("alt", "New Alt Text");
```

## Event Delegation

Event delegation is a powerful technique that involves handling events at a higher level in the DOM hierarchy. This is particularly useful when dealing with dynamically added elements.

```javascript
// Event delegation example
document
  .getElementById("parentContainer")
  .addEventListener("click", function (event) {
    if (event.target.tagName === "BUTTON") {
      // Handle button click
    }
  });
```

## Practical Examples and Mini Projects

### Example: Image Gallery

Create an image gallery that allows users to click on thumbnails to view the full-size image.

### Example: Interactive Quiz

Develop an interactive quiz with questions and multiple-choice answers. Use event delegation to handle user interactions.

### Mini Project: To-Do List with Local Storage

Enhance your previous to-do list by incorporating local storage. This ensures that tasks persist even when the user refreshes the page.

### Mini Project: Dynamic Content Tabs

Build dynamic content tabs that display different information based on user selection. Practice advanced DOM manipulation to achieve this.

Feel free to use these examples and mini projects to solidify your understanding of advanced DOM manipulation and event delegation. Happy coding!

## LinkedIn Post for Achievement

"Day 23 in my coding journey, and I'm mastering advanced DOM manipulation and event delegation in JavaScript! 🚀 From modifying styles to practical examples like image galleries and interactive quizzes, the learning never stops. 💡 #Day23 #100DaysOfCoding #AdvancedJS #WebDevProjects #CodeWithAadi

**Follow us:**

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)

```

Feel free to adjust the content as needed for your context!
```
