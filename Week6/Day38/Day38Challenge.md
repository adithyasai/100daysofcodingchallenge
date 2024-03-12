## Day 38: Object-Oriented Programming in Python

### Introduction to Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a programming paradigm based on the concept of "objects," which can contain data in the form of fields (often known as attributes or properties) and code in the form of procedures (often known as methods). OOP models real-world entities as software objects that have some data associated with them and can perform certain functions.

### Key Concepts of OOP

1. **Classes and Objects:** A class is a blueprint for creating objects. An object is an instance of a class, containing actual values instead of variables.

2. **Attributes and Methods:** Attributes are data stored inside an object or class. Methods are functions defined inside a class that operate on the objects of the class.

3. **Inheritance:** It allows a class to inherit attributes and methods from another class, promoting code reuse.

4. **Encapsulation:** It involves bundling the data and methods that operate on the data within one unit. This keeps the data safe from outside interference and misuse.

5. **Polymorphism:** It allows methods to do different things based on the object it is acting upon, even with the same name.

### Basic Syntax for Classes and Objects

```python
class MyClass:
    # Class attribute
    class_attribute = "This is a class attribute."

    # Initializer / Instance attributes
    def __init__(self, attribute_value):
        self.instance_attribute = attribute_value

    # Method
    def my_method(self):
        return f"Accessing instance attribute: {self.instance_attribute} and class attribute: {self.class_attribute}"

# Creating an object of MyClass
my_object = MyClass("This is an instance attribute.")

# Accessing method using the object
print(my_object.my_method())
```

### Inheritance in Python

Inheritance allows one class (child class) to inherit the attributes and methods of another class (parent class). This promotes code reuse and simplifies maintenance.

```python
class ParentClass:
    def parent_method(self):
        print("This is a parent method.")

class ChildClass(ParentClass):
    def child_method(self):
        print("This is a child method.")

# Creating an object of ChildClass
child = ChildClass()

# Accessing methods from both ParentClass and ChildClass
child.parent_method()
child.child_method()
```

### Encapsulation: Using Private Attributes and Methods

Encapsulation in Python can be achieved by prefixing the name of an attribute or method with a double underscore `__`, which makes it private to the class.

```python
class EncapsulatedClass:
    def __init__(self):
        self.public_attribute = "This is public."
        self.__private_attribute = "This is private."

    def public_method(self):
        return f"Accessing public attribute: {self.public_attribute}"

    def __private_method(self):
        return "This is a private method."

my_obj = EncapsulatedClass()
print(my_obj.public_method())
# The following will raise an error as private_attribute and __private_method are private
# print(my_obj.__private_attribute)
# print(my_obj.__private_method())
```

### Real-Life Example: Implementing a Bank Account Class

Consider a simple `BankAccount` class that encapsulates the concept of a bank account, allowing for deposits, withdrawals, and balance checks.

```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.__balance = balance

    def deposit(self, amount):
        self.__balance += amount
        print(f"Added {amount} to the balance")

    def withdraw(self, amount):
        if amount <= self.__balance:
            self.__balance -= amount
            print(f"Withdrew {amount} from the balance")
        else:
            print("Insufficient balance")

    def get_balance(self):
        return f"The current balance is {self.__balance}"

# Creating an instance of BankAccount
account = BankAccount("John Doe")

# Making some transactions
account.deposit(100)
account.withdraw(50)

# Checking the balance
print(account.get_balance())
```

### Assignment: Build a Library Management System

Your task is to create a simple library management system that can handle books in a library. The system should allow adding books, lending books to users, and checking the availability of books. - (use the example given above)

**Requirements:**

1. Define a `Book` class with attributes like `title`, `author`, and `status` (available, lent).
2. Implement methods in the `Book` class for lending books (`lend_book`) and returning books (`return_book`).
3. Create a `Library` class that holds a collection of books. It should have methods to add books to the library and to check the availability of books.
4. Use encapsulation to ensure that the status of books can only be changed through the `lend_book

## Follow us:

- **Instagram:** [code.with.aadi](https://www.instagram.com/code.with.aadi/)
- **LinkedIn:** [adithyasaladi](https://www.linkedin.com/in/adithyasaladi/), [bhavyasriy](https://www.linkedin.com/in/bhavyasriy/)
- **YouTube:** [@code.with.aadi79](https://www.youtube.com/@Code.with.aadi79)
