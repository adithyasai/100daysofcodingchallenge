## Day 20: Constructors, Prototypes, and ES6 Classes in JavaScript

### Constructors and Prototypes

In JavaScript, **constructors** are special functions used to create instances of objects. The **prototype** is a property available with all JavaScript functions that allows you to add new properties and methods to objects constructors.

**Example with Constructor and Prototype:**

```javascript
function Car(make, model) {
  this.make = make;
  this.model = model;
}

Car.prototype.displayInfo = function() {
  console.log(`This car is a ${this.make} ${this.model}.`);
};

const myCar = new Car('Toyota', 'Corolla');
myCar.displayInfo(); // Output: This car is a Toyota Corolla.
```

**Real-Life Example:** A `Car` constructor function creates car objects. The prototype adds a shared method to all cars, like displaying their info.

ES6 (ECMAScript 2015) introduced classes to JavaScript, providing a new syntax for creating objects and dealing with inheritance. This feature is syntactic sugar over JavaScript's existing prototype-based inheritance and does not introduce a new object-oriented inheritance model.

### Syntax and Structure

An ES6 class starts with the `class` keyword followed by the class name. The class body is enclosed in curly braces `{}`.

```javascript
class MyClass {
  // Class body
}
```

### Constructor Method

The `constructor` method is a special method for creating and initializing objects created with the class. There can only be one `constructor` method in a class.

```javascript
class Car {
  constructor(make, model) {
    this.make = make;
    this.model = model;
  }
}
```

### Instance Methods

Instance methods can be added to the class definition. These methods can be called on instances of the class.

```javascript
class Car {
  constructor(make, model) {
    this.make = make;
    this.model = model;
  }

  displayInfo() {
    console.log(`This car is a ${this.make} ${this.model}.`);
  }
}

const myCar = new Car('Toyota', 'Corolla');
myCar.displayInfo(); // Output: This car is a Toyota Corolla.
```

### Static Methods

Static methods are defined on the class itself, not on the instances of the class. They are called using the class name.

```javascript
class Car {
  static identify() {
    console.log('I am a Car class.');
  }
}

Car.identify(); // Output: I am a Car class.
```

### Inheritance

ES6 classes support inheritance via the `extends` keyword. A class can extend another class, inheriting its properties and methods.

```javascript
class Vehicle {
  constructor(wheels) {
    this.wheels = wheels;
  }

  displayWheels() {
    console.log(`This vehicle has ${this.wheels} wheels.`);
  }
}

class Car extends Vehicle {
  constructor(make, model) {
    super(4); // Calls the parent class's constructor with 4 as the number of wheels
    this.make = make;
    this.model = model;
  }
}

const myCar = new Car('Honda', 'Civic');
myCar.displayWheels(); // Output: This vehicle has 4 wheels.
```

### Getters and Setters

Getters and setters can be used to control access to certain properties of a class.

```javascript
class Person {
  constructor(name) {
    this._name = name;
  }

  get name() {
    return this._name;
  }

  set name(value) {
    this._name = value;
  }
}

let person = new Person('Alice');
console.log(person.name); // Output: Alice
person.name = 'Bob';
console.log(person.name); // Output: Bob
```

### Advantages of ES6 Classes

- **Simpler Syntax:** Classes provide a much simpler and clearer syntax to create objects and deal with inheritance.
- **Readability:** The class syntax is more straightforward, making the code easier to read and understand.
- **Encapsulation:** Classes support encapsulation of data, providing a clear distinction between public and private data and methods.

ES6 classes offer a cleaner, more intuitive syntax for object creation and inheritance in JavaScript, aligning with traditional OOP concepts found in other languages. However, it's essential to understand that under the hood, ES6 classes are still built on top of JavaScript's prototype-based inheritance.

### Assignment : Practice

### LinkedIn Post for Achievement

"Day 20 into my #100DaysOfCoding journey and I've just navigated the world of constructors, prototypes, and ES6 classes in JavaScript! 🚀 Built a simple yet functional ToDo List app. Embracing OOP principles one day at a time! #Day20 #100DaysOfCoding #JavaScriptJourney #codewithaadi

## Follow us:
- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)