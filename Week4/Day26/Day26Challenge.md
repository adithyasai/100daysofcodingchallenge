Certainly! Here's the content for Day 26 in Markdown format:

````markdown
# Day 26: Destructuring Assignment, Spread and Rest Operators, Template Literals, Enhanced Object Literals

## Destructuring Assignment

Destructuring assignment is a convenient way to extract values from arrays or objects and assign them to variables in a concise manner.

### Destructuring Arrays

```javascript
// Destructuring array
const numbers = [1, 2, 3];
const [first, second, third] = numbers;
console.log(first, second, third); // Output: 1 2 3
```
````

### Destructuring Objects

```javascript
// Destructuring object
const person = { name: "John", age: 30, city: "New York" };
const { name, age, city } = person;
console.log(name, age, city); // Output: John 30 New York
```

## Spread and Rest Operators

The spread (`...`) and rest (`...`) operators provide powerful ways to work with arrays and function parameters.

### Spread Operator for Arrays

```javascript
// Spread operator for arrays
const arr1 = [1, 2, 3];
const arr2 = [...arr1, 4, 5];
console.log(arr2); // Output: [1, 2, 3, 4, 5]
```

### Rest Operator for Function Parameters

```javascript
// Rest operator for function parameters
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3, 4, 5)); // Output: 15
```

## Template Literals

Template literals provide a more flexible way to create strings, allowing variable interpolation and multiline strings.

```javascript
// Template literals
const name = "Alice";
const age = 25;

const greeting = `Hello, my name is ${name} and I am ${age} years old.`;
console.log(greeting);
```

## Enhanced Object Literals

Enhanced object literals simplify the syntax for creating objects, making the code more concise.

```javascript
// Enhanced object literals
const firstName = "Bob";
const lastName = "Smith";

const person = {
  firstName,
  lastName,
  greet() {
    console.log(`Hello, ${this.firstName} ${this.lastName}!`);
  },
};

person.greet(); // Output: Hello, Bob Smith!
```

## Real-Life Example: Building a Contact List

```javascript
// Building a contact list using destructuring and enhanced object literals
const contacts = [
  { id: 1, name: "Alice", email: "alice@example.com" },
  { id: 2, name: "Bob", email: "bob@example.com" },
];

// Destructuring and mapping to create a new array of enhanced objects
const enhancedContacts = contacts.map(({ id, name, email }) => ({
  id,
  name,
  email,
}));

console.log(enhancedContacts);
```

In this example, we use destructuring and enhanced object literals to create a new array of contacts with a simplified structure.

## Assignment: Create a Blog Post

Build a simple blog post structure using destructuring, spread and rest operators, template literals, and enhanced object literals.

**Requirements:**

1. Use destructuring to extract information like title, author, and content from an object.
2. Utilize the spread operator to combine multiple arrays or objects.
3. Create a template literal for displaying the blog post.
4. Apply enhanced object literals for more concise object creation.

This assignment will reinforce your understanding of these JavaScript features in a real-world context.

## LinkedIn Post for Achievement

"Day 26 in my coding journey, and I'm harnessing the power of destructuring assignment, spread and rest operators, template literals, and enhanced object literals in JavaScript! 💪 Building a blog post structure showcases the elegance and efficiency of these features. 🚀 #Day26 #100DaysOfCoding #JavaScriptFeatures #WebDevSkills #CodeWithAadi

**Follow us:**

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)

```

Feel free to customize and adapt this content to suit your preferences!
```
