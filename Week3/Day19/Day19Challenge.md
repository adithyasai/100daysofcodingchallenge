## Day 19: Object-Oriented Programming (OOP) in JavaScript

### OOP Concepts

Object-Oriented Programming (OOP) is a programming paradigm based on the concept of "objects", which can contain data and code: data in the form of fields (often known as attributes or properties), and code in the form of procedures (often known as methods).

### Introduction to Objects

In JavaScript, an object is a standalone entity, with properties and type. Think of it as a 'thing' that can perform a set of related activities (methods) and has characteristics (properties).

```javascript
let dog = {
  name: 'Buddy',
  breed: 'Golden Retriever',
  age: 3,
  bark() {
    console.log('Woof!');
  }
};

console.log(dog.name); // Output: Buddy
dog.bark(); // Output: Woof!
```

### Object Properties and Methods

**Properties** are values associated with an object. **Methods** are actions that can be performed on objects. Methods are stored in properties as function definitions.

```javascript
let person = {
  firstName: 'Alice',
  lastName: 'Johnson',
  fullName() {
    return `${this.firstName} ${this.lastName}`;
  }
};

console.log(person.fullName()); // Output: Alice Johnson
```

### Creating Objects and Object Literals

An **object literal** is the simplest way to create an object in JavaScript. It's a list of name-value pairs wrapped in curly braces `{}`.

```javascript
let car = {
  make: 'Toyota',
  model: 'Corolla',
  drive() {
    console.log('Vroom vroom');
  }
};

car.drive(); // Output: Vroom vroom
```

### Real-Life Example

Think of an object as a coffee machine. The machine (object) has properties like brand, model, and water level, and methods like brew() or clean(). When you use the coffee machine, you're interacting with its properties and calling its methods to perform tasks.

### Assignment: Build a Library System

Create a simple library system where you can add books, list all books, and mark a book as read.

**Requirements:**

1. Define a `Book` object with properties like `title`, `author`, `pages`, and `read`.
2. Create methods to add a book, list all books, and mark a book as read.
3. Store all book objects in an array within a `Library` object.

<center><img src="https://github.com/adithyasai/100daysofcodingchallenge/blob/week1/images/week3_ss7.png" width="800" height="400"></center>

**Example Code:**

```javascript
function Book(title, author, pages, read) {
    this.title = title;
    this.author = author;
    this.pages = pages;
    this.read = read;
    this.info = function() {
      return `${this.title} by ${this.author}, ${this.pages} pages, ${this.read ? 'read' : 'not read yet'}`;
    };
}

let Library = {
  books: [],
  addBook(book) {
    //Code
  },
  listBooks() {
    //Code
  }
};

let book1 = new Book('The Hobbit', 'J.R.R. Tolkien', 295, false);
Library.addBook(book1);
Library.listBooks();
```

In this assignment, you're using objects and their associated methods and properties to simulate a real-world library system, applying OOP principles to organize and manage data effectively.

### Object-Oriented Programming (OOP) Concepts

OOP is a programming paradigm based on the concept of objects, which can contain data and code. The main OOP concepts include Encapsulation, Inheritance, Polymorphism, and Abstraction.

### Encapsulation

Encapsulation is the bundling of data (attributes) and methods (functions) that operate on the data into a single unit, or class. It restricts direct access to some of an object's components, which can prevent the accidental modification of data.

**Real-Life Example:** Consider a coffee maker. You interact with it through buttons and dials (the public interface), but you don't need to know about the internal processes to make coffee (the hidden, encapsulated details).

**Example Code:**

```javascript
function CoffeeMaker(brand) {
  let temperature = 90; // Encapsulated property

  this.brand = brand; // Public property

  this.brew = function() { // Public method
    console.log(`Brewing coffee at ${temperature} degrees.`);
  };
}

let myCoffeeMaker = new CoffeeMaker('BrandX');
myCoffeeMaker.brew(); // Output: Brewing coffee at 90 degrees.
```

### Inheritance

Inheritance allows one class to inherit the properties and methods of another. This can promote code reusability.

**Real-Life Example:** A general `Vehicle` class might have properties like speed and methods like move. A `Car` class could inherit from `Vehicle` and have additional properties like fuelType.

**Example Code:**

```javascript
function Vehicle(speed) {
  this.speed = speed;

  this.move = function() {
    console.log(`Moving at ${this.speed} km/h.`);
  };
}

function Car(speed, fuelType) {
  Vehicle.call(this, speed); // Inheritance
  this.fuelType = fuelType;
}

let myCar = new Car(120, 'Diesel');
myCar.move(); // Output: Moving at 120 km/h.
```

### Polymorphism

Polymorphism means "many shapes." It allows objects of different classes to be treated as objects of a common super class.

**Real-Life Example:** A function `drawShape` can draw any shape (circle, square, triangle), even though they have different implementations of the `draw` method.

**Example Code:**

```javascript
function Shape() {}
Shape.prototype.draw = function() {
  return "I am just a generic shape";
};

function Circle() {}
Circle.prototype = Object.create(Shape.prototype);
Circle.prototype.draw = function() {
  return "I am a circle";
};

const shapes = [new Shape(), new Circle()];
shapes.forEach(shape => {
  console.log(shape.draw());
});
// Output: I am just a generic shape
//         I am a circle
```

### Abstraction

Abstraction means hiding complex implementation details and showing only the necessary features of an object.

**Real-Life Example:** A car is a complex machine with many parts, but you only interact with it through interfaces like the steering wheel, pedals, and buttons.

**Example Code:**

```javascript
function Car(model) {
  this.model = model;

  let engineStatus = 'off'; // Private attribute

  function startEngine() { // Private method
    engineStatus = 'on';
    console.log('Engine started');
  }

  this.drive = function() { // Public method
    startEngine();
    console.log(`${this.model} is driving.`);
  };
}

let myCar = new Car('ModelX');
myCar.drive();
// Output: Engine started
//         ModelX is driving.
```

### Assignment: Create a Simple Bank System

Develop a simple banking system that utilizes encapsulation, inheritance, and abstraction.

**Requirements:**

1. Create a `BankAccount` class with properties like `accountNumber` and `balance`. Include methods for `deposit` and `withdraw`.
2. Use encapsulation to protect the balance from direct access.
3. Create a `SavingsAccount` class that inherits from `BankAccount` and includes an `interestRate` property.
4. Implement polymorphism by overriding the `withdraw` method for the `SavingsAccount` to include a withdrawal limit.

<center><img src="https://github.com/adithyasai/100daysofcodingchallenge/blob/week1/images/week3_ss8.png" width="800" height="400"></center>

In this assignment, you'll apply OOP principles to simulate a real-life banking system, organizing and managing data effectively and securely.

### LinkedIn Post for Achievement

"Day 5 of my coding adventure and I've just unlocked the power of OOP in JavaScript! 🚀 From encapsulation to polymorphism, I've crafted a simple bank system that's both secure and efficient. #Day5JavaScript #100DaysOfCoding #OOP #JavaScriptJourney

**Follow my coding adventure and let's grow together!**
- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [Follow me](https://www.linkedin.com/in/your-linkedin-profile/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)"