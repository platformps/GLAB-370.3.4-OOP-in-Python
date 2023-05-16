# GLAB-370.3.4-OOP-in-Python

## Lab Description
This lab focuses on Object-Oriented Programming (OOP) in Python. Object-Oriented Programming is a programming paradigm that emphasizes the concept of objects, which can contain data and code in the form of methods. In this lab, learners will gain hands-on experience with defining classes, creating objects, and working with inheritance and encapsulation in Python.

## Learning Objectives

- Understand the fundamentals of Object-Oriented Programming.
- Define classes and create objects in Python.
- Implement inheritance to create class hierarchies.
- Apply encapsulation principles to control access to class members.
- Use methods, properties, and instance variables effectively.

## Prerequisites
Basic knowledge of Python programming.

## Activities

### 1. Introduction to Classes and Objects
In this activity, learners will be introduced to the concepts of classes and objects in Object-Oriented Programming. They will understand how classes serve as blueprints for creating objects, and how objects encapsulate both data (attributes) and behavior (methods). Examples will be provided to illustrate the relationship between classes and objects.

### 2. Defining and Instantiating Classes
In this activity, learners will learn how to define classes in Python. They will understand the structure of a class, including attributes and methods. Learners will also learn how to create objects (instances) of a class using the class constructor. They will be guided through the process of defining a class, creating objects, and accessing their attributes and methods.

```
# Define a class
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def get_area(self):
        return self.width * self.height

# Create objects of the class
rectangle1 = Rectangle(5, 3)
rectangle2 = Rectangle(4, 6)

# Access attributes and call methods
print(rectangle1.width)  # Output: 5
print(rectangle2.get_area())  # Output: 24
```

**Inheritance and Polymorphism**
In this activity, learners will explore the concept of inheritance in Python. They will understand how inheritance allows the creation of hierarchical relationships between classes, enabling code reuse and promoting modularity. Learners will learn how to define subclasses that inherit attributes and methods from a parent class. Polymorphism, which allows objects of different classes to be used interchangeably, will also be introduced.

```
# Define a parent class
class Shape:
    def __init__(self, color):
        self.color = color

    def get_area(self):
        pass

# Define a subclass
class Rectangle(Shape):
    def __init__(self, width, height, color):
        super().__init__(color)
        self.width = width
        self.height = height

    def get_area(self):
        return self.width * self.height

# Create objects of the classes
shape = Shape("Red")
rectangle = Rectangle(5, 3, "Blue")

# Use objects interchangeably
print(shape.color)  # Output: Red
print(rectangle.color)  # Output: Blue
print(rectangle.get_area())  # Output: 15
```

### 4. Encapsulation and Access Modifiers
In this activity, learners will learn about encapsulation and access modifiers in Python. Encapsulation involves bundling data and methods together, and access modifiers control the visibility and accessibility of class members. Learners will understand the concepts of public, protected, and private members, and how to implement them in Python classes. Examples will be provided to demonstrate the usage of access modifiers.

```
# Define a class with access modifiers
class Person:
    def __init__(self, name, age):
        self._name = name  # Protected attribute
        self.__age = age   # Private attribute

    def display_info(self):
        print(f"Name: {self._name}")
        print(f"Age: {self.__age}")

# Create an object of the class
person = Person("John Doe", 25)

# Access protected attribute
print(person._name)  # Output: John Doe

# Attempt to access private attribute
# print(person.__age)  # This will cause an AttributeError

# Access private attribute using name mangling
print(person._Person__age)  # Output: 25

# Call the method to display information
person.display_info()
```

### 5. Real-world Scenario: Building a Banking System
In this activity, learners will apply their knowledge of Object-Oriented Programming to design and implement a simple banking system. They will define classes for Bank, Account, and Customer, and establish relationships between them using inheritance. Learners will implement methods to perform banking operations such as opening accounts, depositing and withdrawing funds, and generating account statements.


```
class Bank:
    def __init__(self, name):
        self.name = name
        self.accounts = []

    def create_account(self, account):
        self.accounts.append(account)

    def generate_account_statements(self):
        for account in self.accounts:
            print(f"Account Number: {account.account_number}")
            print(f"Customer Name: {account.customer.name}")
            print(f"Balance: {account.balance}")

class Customer:
    def __init__(self, name):
        self.name = name

class Account:
    def __init__(self, account_number, customer):
        self.account_number = account_number
        self.customer = customer
        self.balance = 0

    def deposit(self, amount):
        self.balance += amount

    def withdraw(self, amount):
        if self.balance >= amount:
            self.balance -= amount
        else:
            print("Insufficient balance")

# Create objects and perform banking operations
customer1 = Customer("John Doe")
account1 = Account(12345, customer1)
account1.deposit(1000)
account1.withdraw(500)

customer2 = Customer("Jane Smith")
account2 = Account(54321, customer2)
account2.deposit(2000)

bank = Bank("MyBank")
bank.create_account(account1)
bank.create_account(account2)
bank.generate_account_statements()
```

In this example, we assume a simplified banking system with classes for Bank, Account, and Customer. The Bank class manages multiple accounts and can generate account statements. The Account class represents a customer account and can perform deposit and withdrawal operations. The Customer class holds the customer's information.

You should modify the code according to the specific requirements of the banking system.

## Lab Submission
As part of this lab, you are required to complete the real-world scenario mentioned in Activity 5. Design and implement the classes for the banking system, ensuring proper usage of inheritance, encapsulation, and other OOP principles. Submit your completed Python program file(s) with appropriate comments and any additional instructions if required.

Please ensure that your submitted program is well-documented and follows best practices for coding style and readability.
