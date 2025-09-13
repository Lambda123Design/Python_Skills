# Python_Skills

Following are my Python Skills:

Python Faker Library used to create syntentic data - To generate synthetic real-time transactions, I will use the Python library Faker. [Used in Grafana Project in MLOps Course]

Pytest library is used for unit testing. It is capable of executing Python unit test cases [Used in Automate Testing Workflow With Python in MLOps Course]

"python-box" - A Python Library which can be used for Exception Handling

Libraries: lxml, html5lib, beautifulsoup4, openpyxl, pickle

1. **Basics Python:**
   
(A) **Basics Python:**

  (i) Syntax and Semantics
  
  (ii) Single and Multi Line Commands

(B). **Variables:**
   (i) Declaring and Assigning Variables
   
   (ii) Naming Conventions
   
   (iii) Variable Types
   
   (iv) Type Checking and Conversion
   
   (v) Dynamic Typing

(C) . **Data Types:**

   (i) Basic Data Types: int, float, boolean, str
   
   (ii) Type Conversion

(D) . **Operators:**

   (i) Arithmetic Operators - Addition, Multiplication, Division, Floor Divison, Modulus, Exponential
   
   (ii) Comparison Operators - Equal to, Not equal to, Greater than, Lesser than, Greater than or equal to, Lesser than or equal to
   
   (iii) Logical Operators - AND, OR, NOT

(E). **Conditional Statements:**

   (i) if statement
   
   (ii) else statement
   
   (iii) elif statement
   
   (iv) Nested Conditional Statements

(F). **Loops:**
   (i) for Loop: Iterating over a string, Iterating over a range
   
   (ii) while Loop
   
   (iii) Loop Control Statements: break, continue, pass
   
   (iv) Nested Loops

2. **File Handling**:

   (i) File Operation - With Open (r-Read, w-Write,a-Append,wb-WriteBytes,w+ - Read and Write); file.write,file.writelines, file.seek(0) - Takes the cursor to the beginning while read and write.
   
   (ii) Working with File Paths - mkdir - Make Directory, listdir - List Directory, getcwd - Current Working Directory, path.exists - Check if path exists, .isfile - Check if it is a file, .isdir - Check if it is a directory, path.abspath - Gives Absolute path

3. **Exception Handling**:

  (i) Try, Except Block
  
  (ii) Try, Except, Else Block
  
  (iii) Try, Except, Else, Finally Block


**21. OOPS with Class and Objects**

Object-Oriented Programming (OOP) is a programming paradigm that uses "objects" to design applications and computer programs. OOP allows for modeling real-world scenarios using classes and objects. This lesson covers the basics of creating classes and objects, including instance variables and methods.

**Object Example --> Calling from the Class; tesla1=Tesla(4,5,"electric",True) tesla1.selfdriving()**

   **(i) Class and Objects:**
   
   Class is a blue print for creating objects. Attributes,methods. class Car: pass; audi=Car(); **Car is a class and Audi is an Object of the class**

   audi.windows=4; print(audi.windows) --> Windows is an attribute that is present inside the Object (This is not a proper way because if I create next for Tata.doors, I will get an error because I didn't create anything called as Windows for Tata) 

   **We will learn an efficient way on how we can initialize the attributes while we are creating the objects itself**

   dir(tata) --> If we give this, we can learn all the directiories inside this, we can see door inside it as we created it. 

   **We will learn specifically about __init__ inside it. __init__ is known as Constructor**
   
   ## Instance Variables and Methods
   class Dog:
    ## constructor
    def __init__(self,name,age):
        self.name=name
        self.age=age

**self is used Globally. We can use anything like Krish, Ashwath. But to use it inside the Method also we can use the Instance Variable**

**We make sure that whenever we create an object we need to give 2 variables inside it. Self is responsible in accessing the instance variable inside the class itself whenever we create the object. Name is the Instance variable available inside the Dog Class. Two Parameters are name and age. If I print, it shows what instance variable is created at which Location. Whatever defined in the constructor only those can be mentioned**

**Instance Variables - Theyare something that talks about Dog. Say name and age are something that talks about an Object (Attributes)**

**Instance Methods - Methods are something say like a Dog can be Barking, It can be doing some kind of Functionalities, say it can be running at a specific speed**

## Define a class with instance methods
class Dog:
    def __init__(self,name,age):
        self.name=name
        self.age=age
    def bark(self):
        print(f"{self.name} says woof")


dog1=Dog("Buddy",3)
dog1.bark()
dog2=Dog("Lucy",4)
dog2.bark()

**Valid Examples:**

## Define a class for bank account
class BankAccount:
    def __init__(self,owner,balance=0):
        self.owner=owner
        self.balance=balance
    def deposit(self,amount):
        self.balance+=amount
        print(f"{amount} is deposited. New balance is {self.balance}")
    def withdraw(self,amount):
        if amount>self.balance:
            print("Insufficient funds!")
        else:
            self.balance-=amount
            print(f"{amount} is withdrawn. New Balance is {self.balance}")
    def get_balance(self):
        return self.balance

   **(ii) Inheritance:**

   Inheritance is a fundamental concept in Object-Oriented Programming (OOP) that allows a class to inherit attributes and methods from another class. This lesson covers single inheritance and multiple inheritance, demonstrating how to create and use them in Python.

   ## Parent class
class Car:
    def __init__(self,windows,doors,enginetype):
        self.windows=windows
        self.doors=doors
        self.enginetype=enginetype
    def drive(self):
        print(f"The person will drive the {self.enginetype} car ")

   car1=Car(4,5,"petrol")
   car1.drive()
        
   **Let's Say I have defined this class, and again I want to define another class "Tesla", I can inherit from here, I don't have to write my code again for the class "Tesla". Same in Tesla even we have windows, engines. Instead, we can inherit from earlier**

   **Inheritance:**

   **super --> Inheriting from Parent Class; class child_class(Parent_Class)**

   **Single Inheritance:**
  
   class Tesla(Car):
    def __init__(self,windows,doors,enginetype,is_selfdriving):
        super().__init__(windows,doors,enginetype)
        self.is_selfdriving=is_selfdriving
    def selfdriving(self):
        print(f"Tesla supports self driving : {self.is_selfdriving}")

   tesla1=Tesla(4,5,"electric",True) tesla1.selfdriving()

   **Multiple Inheritance: - When a class inherits from more than one base class**

## Base class 1
class Animal:
    def __init__(self,name):
        self.name=name
    def speak(self):
        print("Subclass must implement this method")

## BAse class 2
class Pet:
    def __init__(self, owner):
        self.owner = owner

##Derived class
class Dog(Animal,Pet):
    def __init__(self,name,owner):
        Animal.__init__(self,name)
        Pet.__init__(self,owner)
    def speak(self):
        return f"{self.name} say woof"
    

## Create an object
dog=Dog("Buddy","Krish")
print(dog.speak())
print(f"Owner:{dog.owner}")


**(iii) Polymorphism:**

**Polymorphism is a core concept in Object-Oriented Programming (OOP) that allows objects of different classes to be treated as objects of a common superclass. It provides a way to perform a single action in different forms. Polymorphism is typically achieved through method overriding and interfaces**

**a) Polymorphism using Method Overriding:**

**Method overriding allows a child class to provide a specific implementation of a method that is already defined in its parent class.**

## Base Class
class Animal:
    def speak(self):
        return "Sound of the animal"
    
## Derived Class 1
class Dog(Animal):
    def speak(self):
        return "Woof!"
    
## Derived class
class Cat(Animal):
    def speak(self):
        return "Meow!"
    
## Function that demonstrates polymorphism
def animal_speak(animal):
    print(animal.speak())
    
dog=Dog()
cat=Cat()
print(dog.speak())
print(cat.speak())
animal_speak(dog)

**Method Overriding --> Same method is getting overridden in the derived class implementation**

**We have Overridden from the Base Class till the Child Class**

**Very Good Example Below for PolyMorphism using Functions and Methods**

### Polymorphissm with Functions and MEthods
## base class
class Shape:
    def area(self):
        return "The area of the figure"
    
## Derived class 1
class Rectangle(Shape):
    def __init__(self,width,height):
        self.width=width
        self.height=height
    def area(self):
        return self.width * self.height
    
##DErived class 2

class Circle(Shape):
    def __init__(self,radius):
        self.radius=radius
    def area(self):
        return 3.14*self.radius *self.radius
    
## Fucntion that demonstrates polymorphism

def print_area(shape):
    print(f"the area is {shape.area()}")


rectangle=Rectangle(4,5)
circle=Circle(3)

print_area(rectangle)
print_area(circle)

**We are Over riding the Area formula again for a rectangle because the formula will be different. We are redifing the function for the derieved class**

**b) Polymorphism using Interfaces:**

**In other Programming languages we call it as Interfaces, but in Python we call it as Abstract Base Classes**

**Abstract Base Classes (ABCs) are used to define common methods for a group of related objects. They can enforce that derived classes implement particular methods, promoting consistency across different implementations.**

from abc import ABC,abstractmethod

## Define an abstract class
class Vehicle(ABC):
    @abstractmethod
    def start_engine(self):
        pass

## Derived class 1
class Car(Vehicle):
    def start_engine(self):
        return "Car enginer started"
    
## Derived class 2
class Motorcycle(Vehicle):
    def start_engine(self):
        return "Motorcycle enginer started"
    
# Function that demonstrates polymorphism
def start_vehicle(vehicle):
    print(vehicle.start_engine())

## create objects of cAr and Motorcycle

car = Car()
motorcycle = Motorcycle()

start_vehicle(car)

**(iv) Encapsulation**

The discussion continues with Python, focusing on object-oriented programming concepts. Two important concepts are encapsulation and abstraction. The content is divided into two parts: encapsulation is discussed in the current section, and abstraction is left for the next one. Both concepts are essential for designing maintainable and reusable code.

Encapsulation and Abstraction Overview

Encapsulation involves bundling data (variables) and methods that operate on the data into a single unit.

Abstraction involves hiding complex implementation details while exposing only necessary features.

Encapsulation restricts direct access to some object components, preventing accidental interference and misuse of data.

In this discussion, only encapsulation is covered, while abstraction is reserved for the next part.

Encapsulation Explanation

Encapsulation is the concept of wrapping data (variables) and methods together as a single unit.

It restricts direct access to certain object components.

Encapsulation can be implemented using getter and setter methods.

Before explaining getters and setters, three important access levels are introduced: public, protected, and private.

Public Variables

By default, instance variables such as self.name and self.age are considered public.

Public variables can be accessed from outside the class.

Example:

A Person class is created with name and age.

An object is created with values.

person.name and person.age can be directly accessed and printed.

Public variables are visible when checking the object’s attributes using dir().

Getter Example with Public Variables

A function get_name(person) can return person.name.

This demonstrates retrieving a public variable outside the class.

Private Variables

Certain attributes may need to be hidden or restricted from direct modification.

Private variables are created by prefixing variable names with double underscores (__).

Example: self.__name and self.__age.

These private variables are not directly visible when dir() is used. Instead, they appear with name mangling in the format _ClassName__variable.

Direct access such as person.__name will fail, producing an error.

Developers may still access the variables using their mangled names (e.g., _Person__name), but this is not good practice.

Private variables emphasize restricted access, indicating they should remain hidden.

Protected Variables

Protected variables are defined with a single underscore prefix (_variable).

They cannot be accessed outside the class directly, but they can be accessed in derived (child) classes.

Example:

A Person class has a protected variable _name.

An Employee class inherits from Person.

Inside Employee, the protected variable _name can be accessed.

Although Python does not strictly enforce protected rules, convention dictates that protected variables should only be accessed within subclasses.

Encapsulation with Getter and Setter Methods

Encapsulation is typically implemented using getter and setter methods to safely access and modify private variables.

Example:

Person class contains private variables __name and __age.

A getter method get_name() is used to retrieve the private __name.

A setter method set_name(name) is used to modify the private __name.

Similarly, get_age() retrieves __age and set_age(age) updates it.

A condition is applied in set_age to ensure age cannot be negative (if age ≤ 0, an error message is displayed).

Analogy for Encapsulation

Encapsulation is compared to a washing machine: users can access buttons and inputs, but the internal mechanism is hidden. Similarly, in programming, only necessary methods are exposed, while internal details (variables) are hidden.

Example Execution

A Person object is created with ("Krish", 34).

get_name() prints "Krish".

get_age() prints "34".

set_age(35) modifies age, and get_age() prints "35".

set_age(-5) fails with the message "age cannot be negative".

Key Points Summarized

Public variables: accessible anywhere in the program.

Private variables: cannot be accessed outside the class (not even in derived classes). They require getter and setter methods for interaction.

Protected variables: accessible within the class and its subclasses, but not recommended to be accessed directly from outside.

In Python, these access controls are based on conventions rather than strict enforcement.

Encapsulation ensures that important attributes remain hidden and are only accessed or modified through controlled methods.

The explanation concludes by stating that encapsulation was fully covered, including examples of public, private, and protected variables, as well as getter and setter methods. The next part will discuss abstraction in detail.

**(v) Abstraction**

Definition:

Abstraction is one of the core pillars of Object-Oriented Programming (OOP).

It is the concept of hiding the complex implementation details and showing only the necessary features of an object.

This helps in reducing programming complexity and development effort.

Real-World Examples of Abstraction

Washing Machine

The user sees only buttons (start, timer, dryer, etc.).

The internal process (motor, water flow, drying mechanism) is hidden.

Buttons = exposed features, internal mechanisms = hidden implementation.

Other Examples

Mobile phones: users press icons, but internal processing remains hidden.

AC remote: pressing power or temperature buttons hides the underlying electronics.

Laptop/Desktop: pressing "Shutdown" hides how processes are terminated in RAM and CPU.

These examples demonstrate features are exposed while complexities are hidden.

Abstraction in Python (Using Code)

Python provides abstraction through Abstract Classes and Abstract Methods, which are available in the abc module.

Step 1: Importing Abstract Base Class
from abc import ABC, abstractmethod


ABC → stands for Abstract Base Class.

Used as a parent class for abstract classes in Python.

Step 2: Creating an Abstract Class
class Vehicle(ABC):  # Abstract class inheriting ABC
    def drive(self):
        print("The vehicle is used for driving.")   # Normal method
    @abstractmethod
    def start_engine(self):  # Abstract method
        pass


Normal Method (drive): implemented inside the abstract class.

Abstract Method (start_engine): declared but not implemented (empty function).

Step 3: Creating a Child Class
class Car(Vehicle):   # Car inherits Vehicle
    def start_engine(self):  # Must implement abstract method
        print("Car engine started")


Any class that inherits an abstract class must implement all abstract methods.

If not implemented, Python throws an error.

Step 4: Using Abstraction
def operate_vehicle(vehicle):
    vehicle.start_engine()   # Calls abstract method (implemented by child class)
    vehicle.drive()          # Calls normal method from base class

car = Car()
operate_vehicle(car)


Output:

Car engine started
The vehicle is used for driving.

How Abstraction Works Here

The Vehicle class exposes only features (drive, start_engine) to child classes.

The implementation of start_engine is hidden and left for child classes like Car to define in their own way.

drive() is shared and can be directly used.

Thus, abstraction provides a blueprint while hiding the internal complexity.

Key Points on Abstraction in Python

Abstract Class

Created by inheriting from ABC.

Cannot be instantiated directly.

Abstract Method

Defined using @abstractmethod decorator.

Must be implemented by child classes.

Normal Methods

Can coexist in abstract classes.

Directly available to child classes.

Purpose

Shows only essential features.

Hides complex logic.

Enforces child classes to implement specific functionality.

Short Definition Recap

Abstraction: Hiding complex implementation details and exposing only the required features of an object.

**(vi) Magic Methods In Python**

Magic methods in Python are also known as dunder methods (short for double underscore methods). They are special methods that start and end with double underscores.

These methods allow you to define the behavior of objects for built-in operations such as initialization, string representation, arithmetic operations, and comparisons.

Examples of Magic Methods

__init__: Initializes a new instance of a class. It is the constructor method in Python.

__str__: Returns a string representation of an object, mainly used when printing an object.

__repr__: Returns the official string representation of an object, mainly used for debugging.

Magic methods are automatically available to any class. To see them, the built-in dir() function can be used on a class or object.

Example:

class Person:
    pass

print(dir(Person))


The output will display all the available magic methods for the Person class.

Overriding Magic Methods

By default, printing an object displays its type and memory location. This behavior can be changed by overriding methods such as __str__ and __repr__.

Example:

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def __str__(self):
        return f"This is {self.name}, {self.age} years old."
    def __repr__(self):
        return f"Person(name={self.name}, age={self.age})"

person = Person("Krush", 34)

print(person)          # Calls __str__
print(repr(person))    # Calls __repr__


Output:

This is Krush, 34 years old.
Person(name=Krush, age=34)

Here:

__str__ was overridden to return a custom message when printing the object.

__repr__ was overridden to return a detailed representation useful for debugging.

Summary:

Magic methods define how objects behave with built-in operations. They provide default functionality for classes, but can be overridden to customize behavior.

Examples include:

__init__ for initialization

__str__ for human-readable string representation

__repr__ for unambiguous string representation

These methods are an essential part of Python’s object-oriented design, and they form the foundation for more advanced topics such as operator overloading.

**(vii) Operator Overloading In Python**

Operator overloading is a feature in Python that allows developers to redefine the behavior of operators for user-defined classes. This is achieved by overriding special magic methods associated with each operator.

By default, operators such as +, -, *, /, ==, <, > work with built-in data types. With operator overloading, the same operators can be customized to work with user-defined objects.

Examples of Operator Magic Methods

__add__: Defines behavior for the + operator

__sub__: Defines behavior for the - operator

__mul__: Defines behavior for the * operator

__truediv__: Defines behavior for the / operator

__eq__: Defines behavior for the == operator

__lt__: Defines behavior for the < operator

__gt__: Defines behavior for the > operator

Implementing Operator Overloading

Example using a Vector class:

class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y
    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)
    def __sub__(self, other):
        return Vector(self.x - other.x, self.y - other.y)
    def __mul__(self, other):
        return Vector(self.x * other, self.y * other)
    def __eq__(self, other):
        return self.x == other.x and self.y == other.y
    def __repr__(self):
        return f"Vector({self.x}, {self.y})"

Using the Overloaded Operators
v1 = Vector(2, 3)
v2 = Vector(4, 5)

print(v1 + v2)      # Vector(6, 8)
print(v1 - v2)      # Vector(-2, -2)
print(v1 * 3)       # Vector(6, 9)
print(v1 == v2)     # False


In this example:

The + operator adds two vectors by summing their x and y coordinates.

The - operator subtracts the coordinates.

The * operator multiplies a vector by a scalar.

The == operator checks equality of two vectors.

Assignment Example: A common exercise is to implement operator overloading for complex numbers. Define a class with real and imaginary parts, and overload operators such as +, -, and * to perform operations on complex numbers.

Conclusion: Operator overloading, combined with magic methods, is a powerful feature in Python. It allows developers to extend the behavior of built-in operators to user-defined objects, making code more readable and expressive for applications such as mathematical operations, custom data structures, and domain-specific models.

**(viii) Custom Exception Handling**

In Python, exceptions provide a way to handle errors that occur during program execution. Apart from using built-in exceptions, it is possible to define custom exceptions. Custom exceptions allow developers to handle specific error scenarios in applications more clearly and effectively.

Creating a Custom Exception

A custom exception can be created by defining a class that inherits from the built-in Exception class. Often, a base error class is created first, and then specific exceptions can inherit from it.

Example:

class Error(Exception):
    """Base class for custom exceptions"""
    pass

class DOBException(Error):
    """Exception raised for invalid date of birth"""
    pass


Here:

Error is a generic base exception class.

DOBException inherits from Error and is used to handle invalid date of birth cases.

Example Scenario

Consider a competitive exam form where the valid age of applicants must be between 20 and 30. If the entered age does not fall within this range, a custom exception should be raised.

try:
    year = int(input("Enter your year of birth: "))
    current_year = 2024
    age = current_year - year
    if 20 <= age <= 30:
        print("Age is valid. You can apply for the exam.")
    else:
        raise DOBException

except DOBException:
    print("Your age should be greater than 20 and less than 30 for this exam.")

How It Works

The user enters the year of birth.

The age is calculated from the current year.

If the age lies between 20 and 30, the input is considered valid.

Otherwise, a DOBException is raised.

The exception is caught in the except block, and a custom error message is displayed to the user.

Use in Applications

Custom exceptions are especially useful in large projects where:

Multiple error scenarios need to be handled separately.

Specific error messages must be shown to users.

Logging and debugging require precise error identification.

Conclusion: Custom exceptions allow developers to define error conditions specific to their applications. By raising and handling these exceptions, programs become more robust, readable, and user-friendly.

# 12. Advance Python:

**(i) Iterators In Python**

Iterators are an advanced Python concept that allows efficient looping and memory management. They provide a way to access elements of a collection sequentially without exposing the underlying structure.

Iterating a List

A list can be traversed directly using a for loop.

my_list = [1, 2, 3, 4, 5, 6]

for i in my_list:
    print(i)

print(type(my_list))       # <class 'list'>
print(my_list)             # [1, 2, 3, 4, 5, 6]

Creating an Iterator

An iterator can be created from a list using the iter() function.

my_list = [1, 2, 3, 4, 5, 6]
iterator = iter(my_list)

print(type(iterator))   # <class 'list_iterator'>
print(iterator)         # <list_iterator object at memory_location>


Unlike a list, printing an iterator does not display its elements. Instead, it points to a memory location where the elements are accessed lazily.

Accessing Elements Using next()

The next() function retrieves elements from the iterator one at a time.

print(next(iterator))   # 1
print(next(iterator))   # 2
print(next(iterator))   # 3
print(next(iterator))   # 4
print(next(iterator))   # 5
print(next(iterator))   # 6

After the last element, calling next() again raises a StopIteration error.

Handling StopIteration Exception

The StopIteration exception can be handled using a try-except block.

my_list = [1, 2, 3, 4, 5, 6]
iterator = iter(my_list)

while True:
    try:
        print(next(iterator))
    except StopIteration:
        print("There are no elements in the iterator")
        break

This ensures that the iteration stops gracefully after all elements are exhausted.

Iterators with Strings

The iter() function can also be used with strings.

my_string = "HELLO"
iterator = iter(my_string)

print(next(iterator))   # H
print(next(iterator))   # E

Each call to next() retrieves the next character in the string.

Summary:

Iterators enable sequential access to elements without exposing internal structure.

They use lazy loading, which means elements are accessed one by one only when required.

iter() creates an iterator and next() retrieves elements.

Once elements are exhausted, StopIteration is raised.

Iterators can be applied to lists, strings, and other iterable objects.

**(ii) Generators With Practical Implementation**

Generators are a simple and powerful way to create iterators in Python. They are a subclass of iterators and are defined using functions along with the yield keyword. Generators produce values lazily, which means they generate values on the fly and do not store them in memory, resulting in efficient looping and memory management.

Creating a Simple Generator

A generator function is written like a normal function, but instead of using return, it uses yield to return values one at a time.

def square(n):
    for i in range(n):
        yield i * i

Example
for val in square(3):
    print(val)


Output

0
1
4


The yield keyword saves the state of the function and returns the value.

On the next iteration, execution resumes from the point where it left off.

Using next() with Generators

A generator can also be iterated using the next() function.

gen = square(3)

print(next(gen))  # 0
print(next(gen))  # 1
print(next(gen))  # 4
print(next(gen))  # StopIteration error after last element


The StopIteration exception occurs once all values have been generated.

Multiple Yields in a Generator

Generators can yield multiple values sequentially.

def my_generator():
    yield 1
    yield 2
    yield 3

gen = my_generator()

print(next(gen))  # 1
print(next(gen))  # 2
print(next(gen))  # 3


Or, using a loop:

for val in my_generator():
    print(val)


Output

1
2
3

Practical Example: Reading Large Files

Generators are particularly useful for handling large datasets or files, as they allow processing one element at a time without loading the entire content into memory.

def read_large_file(file_path):
    with open(file_path, 'r') as file:
        for line in file:
            yield line

file_path = "large_file.txt"

for line in read_large_file(file_path):
    print(line.strip())


Here, the file is read line by line using yield, ensuring that only one line is in memory at any given time.

Difference Between Iterators and Generators

Creation

Iterators are created using the iter() function.

Generators are created using functions with the yield keyword.

Syntax

Iterators require implementing methods like __iter__() and __next__().

Generators automatically provide these methods.

Efficiency

Iterators provide sequential access but may need more boilerplate code.

Generators provide a compact way to write iterators with better memory efficiency.

Summary:

Generators are subclasses of iterators that use the yield keyword.

They generate values lazily, one at a time, without storing them in memory.

They can be iterated using for loops or the next() function.

Generators are especially useful for handling large datasets or files.

**(iii) Function Copy,Cloures And Decorators**

Decorators are an advanced feature in Python that allow modification of the behavior of a function or class method without changing the actual source code of that function. They provide a flexible way to extend functionality and are widely used in frameworks such as Flask and Django.

Definition

A decorator is a function that takes another function as an argument and extends or alters its behavior. This is achieved by wrapping the original function inside another function (closure).

Key Idea:
Decorators add functionality to functions or methods without modifying their original code.

Prerequisite Concepts

Before understanding decorators, it is necessary to understand two concepts:

a) Function Copy

In Python, functions are treated as first-class objects. This means:

A function can be assigned to a variable.

A function can be passed as an argument to another function.

A function can be returned from another function.

Example

def welcome():
    return "Welcome to the Advanced Python course"

# Assigning function to another variable
well = welcome
print(well())   # Welcome to the Advanced Python course

# Deleting the original function
del welcome
print(well())   # Still works


Even after deleting welcome, the copied reference well still executes the function.

b) Closures

A closure is a function defined inside another function that has access to variables from the outer function, even after the outer function has finished execution.

Example

def main_welcome():
    message = "Welcome"
    def sub_welcome():
        print("Welcome to the Advanced Python course")
        print(message, "everyone")
    return sub_welcome

func = main_welcome()
func()


Output

Welcome to the Advanced Python course
Welcome everyone


Here, sub_welcome() is able to access the message variable defined in main_welcome().

Closures are the foundation of decorators, since decorators wrap one function inside another.

Creating a Simple Decorator

A decorator can be defined manually using closures.

def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called")
        func()
        print("Something is happening after the function is called")
    return wrapper


Using the decorator:

@my_decorator
def say_hello():
    print("Hello")

say_hello()


Output

Something is happening before the function is called
Hello
Something is happening after the function is called

Decorators with Arguments

Decorators can also take arguments to modify behavior dynamically.

def repeat(n):
    def decorator(func):
        def wrapper(*args, **kwargs):
            for _ in range(n):
                func(*args, **kwargs)
        return wrapper
    return decorator


Using the decorator with arguments:

@repeat(3)
def say_hello():
    print("Hello")

say_hello()


Output

Hello
Hello
Hello


Here, the function say_hello is executed three times because of the argument passed to the decorator.

Practical Example of a Decorator
def log_decorator(func):
    def wrapper(*args, **kwargs):
        print(f"Function {func.__name__} started")
        result = func(*args, **kwargs)
        print(f"Function {func.__name__} finished")
        return result
    return wrapper

@log_decorator
def add(a, b):
    return a + b

print(add(5, 3))


Output

Function add started
Function add finished
8


This example shows how decorators can be used for logging without modifying the original add function.

Summary:

Functions in Python are first-class objects and can be copied, passed, or returned.

Closures allow a function inside another function to access variables of the enclosing function.

Decorators use closures to wrap functions and extend their behavior.

They are written using the @decorator_name syntax above the function definition.

Decorators can also take arguments, making them more flexible.

Common use cases include logging, authentication, timing functions, and input validation.


# 48. **Python for Data Analysis:**

   (i) NumPy - (np.array), arr.reshape(1,5) - 2D will be in [[]], np.arrange(0,10,2).reshape(5,1) , np.ones ((3,1)), np.eye(3), 
   
   Universal Operations - arr1+arr2, arr1-arr2, arr1*arr2, np.sqrt(arr1), np.sin(arr1), np.log(arr), np.exp(arr)

   Array Slicing and Indexing - arr[0][0], arr[1:,2:], a[0][0]=100

   Statistical Concepts: Standardization and Normalization; np.mean(), np.median(), np.mode(), np.std(), np.var()

   Logical operation: data=np.array([1,2,3,4,5,6,7,8,9,10]); data[(data>=5) & (data<=8)]

   (ii) Pandas (DataFrame (2D) and Series (1D)) - pd.Series(data,index=index), pd.DataFrame(data), type(df['Name']) - Series, df.loc, df.iloc, df.at[1,'Age'], df.iat[2,2], df.drop('Salary',axis=1,inplace-True), df['Age']=df['Age']+1

   (iii) Data Analysis and Manipulation: Renaming Columns - df.rename(columns={'Date':'Sales Date'}); Change Datatypes - df[value_new]=df[value].astype(float); Lambda Function - df['Value_New']=df['Value'].apply(lambda x:x*2)

   Data Aggregattion and Grouping - grouped_mean=df.groupby('Product')['Value'].mean()  
                                    grouped_sum=df.groupby(['Product','Region'])['Value'].sum()
                                    groudped_agg=df.groupby('Region')['Value'].agg(['mean','sum','count'])

   Merging DataFrames: pd.merge(df1,df2,on="Key",how="inner")

   **(iii) Polymorphism:**

   **Polymorphism is a core concept in Object-Oriented Programming (OOP) that allows objects of different classes to be treated as objects of a common superclass. It provides a way to perform a single action in different forms. Polymorphism is typically achieved through method overriding and interfaces**

   **Method Overriding - Method overriding allows a child class to provide a specific implementation of a method that is already defined in its parent class.**

   **Method Overriding: Let's say my Parent Class Dog makes sound as "whoof", My inherited child class makes sound as "whoof" "whoof" "whoof". It allows a child class to provide a specific implementation of a method that is already defined in its parent class**


  ** 49. Read Data from Various Sources:**

df=pd.read_json(StringIO(Data)), df.to_json(orient='index'), df=pd.read_csv(),df.to_csv(), df=pd.read_html(url) (Need 3 Libraries - 'lxml, html5lib, beautifulsoup4'), pd.read_html(url,match="Country",header=0)[0], pd.read_excel  (Need openpyxl), df_excel.to_pickle(), pd.read_pickle(), 


**50.SQLite and Python:**

SQL (Structured Query Language) is a standard language for managing and manipulating relational databases. SQLite is a self-contained, serverless, and zero-configuration database engine that is widely used for embedded database systems. In this lesson, we will cover the basics of SQL and SQLite, including creating databases, tables, and performing various SQL operations.

**It will create a DB in similar way that we have notebooks in Options in VS Code. We will also create a Cursor Object, so that it will iterate through rows and columns**

**commit is important whenever we do a CRUD Operation**

**Bulk Insert - Executemany**

**Closing Connection - connection.close()**

import sqlite3

## Connect to an SQLite database
connection=sqlite3.connect('example.db')
connection

cursor=connection.cursor()

## Create a Table
cursor.execute('''
Create Table If Not Exists employees(
    id Integer Primary Key,
    name Text Not Null,
    age Integer,
    department text
    )
''')

## Commit the changes
connection.commit()

## Insert the data in sqlite table
cursor.execute('''
Insert Into employees(name,age,department)
               values('Krish',32,'Data Scientist')

''')

cursor.execute('''
INSERT INTO employees (name, age, department)
VALUES ('Bob', 25, 'Engineering')
''')

cursor.execute('''
INSERT INTO employees (name, age, department)
VALUES ('Charlie', 35, 'Finance')
''')

## commi the changes
connection.commit()

## Query the data from the table
cursor.execute('Select * from employees')
rows=cursor.fetchall()

## print the queried data

for row in rows:
    print(row)

**Refer Notebook for further working with SQLite**


# 51. Introduction To MultiThreading With Python

**(i) What is Process and Threads**

Multithreading and multiprocessing are fundamental concepts in Python (and in programming in general) that enable writing efficient applications by utilizing concurrency and parallelism. Before exploring these advanced concepts, it is important to understand the basics of programs, processes, and threads.

a) Program

Definition
A program is a sequence of instructions written in a programming language. These instructions describe how a particular task should be performed by a computer.

Examples

Google Chrome (application written as a program using a language like C++).

Microsoft Word or Excel.

Any Python script created by a developer.

Note
A program itself is just static code. Execution of the program transforms it into a process.

b). Process

Definition
A process is an instance of a program that is currently being executed.

Double-clicking the Google Chrome application starts a new process.

Each opened browser window represents a separate process.

Key Characteristics of a Process

Resources required:

Code segment – program instructions.

Data segment – global and static variables.

Heap – dynamically allocated memory.

Stack – local variables and function calls.

Registers – small, fast memory used for temporary storage.

Memory space: Each process has its own separate memory space.

Isolation: One process cannot corrupt another because of independent memory allocation.

Disadvantage: Switching between processes requires more execution time due to the overhead of managing independent memory spaces.

Examples of Processes

Multiple instances of Google Chrome.

Opening Excel files (each runs as a process).

Applications listed in Task Manager (Calculator, OBS Studio, Notepad++, etc.).

c). Thread

Definition
A thread is the smallest unit of execution within a process.

Threads share the code segment, data segment, and heap of their parent process.

Each thread has its own stack and registers for independent execution.

Types of Threads

Single-threaded Process

Contains only one thread.

Example: Running a simple program with a single sequence of execution.

Multi-threaded Process

Contains multiple threads that execute concurrently within the same process.

Each thread has its own stack and registers but shares the rest of the process memory.

Examples of Threads in Applications

MS Paint:

Drawing a rectangle creates a new thread within the Paint process.

Drawing a circle creates another thread.

Excel:

Selecting text and applying “Bold” creates a thread to perform that action.

d). Difference Between Process and Thread
Aspect	Process	Thread
Definition	Instance of a program in execution	Unit of execution within a process
Memory Space	Each process has its own memory	Threads share memory of the process
Resource Overhead	Higher (separate allocation)	Lower (shared memory)
Communication	More complex (Inter-Process Communication, IPC)	Easier (since memory is shared)
Isolation	One process cannot corrupt another	A faulty thread may affect others within the same process

Summary:

A program is a sequence of instructions written in a programming language.

A process is an executing instance of a program, with its own memory and resources.

A thread is the smallest execution unit inside a process, sharing most resources with the parent process but maintaining its own stack and registers.

Processes provide isolation, while threads provide efficiency within a single process.

In upcoming sections, multithreading and multiprocessing in Python can be implemented using modules such as threading and multiprocessing to efficiently manage tasks.

**(ii) Multithreading Practical Implementation With Python**

This section focuses on multithreading, its use cases, and implementation in Python.

When to Use Multithreading

Multithreading should be used in two important cases:

a) I/O Bound Tasks

Tasks that spend more time waiting for input-output operations such as file operations or network requests.

Multithreading allows execution of other tasks while one task is waiting.

b) Concurrent Execution

Used when there is a need to improve the throughput of the application by performing multiple operations concurrently.

Implementation in Python

To implement multithreading:

Import required libraries:

import threading
import time


Define functions:

def print_numbers():
    for i in range(5):
        print(f"Number: {i}")
        time.sleep(2)   # Simulating I/O operation
        
def print_letters():
    for letter in "ABCD":
        print(f"Letter: {letter}")
        time.sleep(2)   # Simulating I/O operation


Without Threads (Sequential Execution):

Both functions are called one after the other.

Execution is strictly line by line.

Since each function contains a delay (time.sleep), the overall execution time increases significantly.

With Threads (Concurrent Execution):

Threads are created for both functions:

t1 = threading.Thread(target=print_numbers)
t2 = threading.Thread(target=print_letters)


Start the threads:

t1.start()
t2.start()


Wait for both threads to complete:

t1.join()
t2.join()


Threads run concurrently. While one thread is waiting during time.sleep, the other continues execution.

Overall execution time reduces approximately to half compared to sequential execution.

Example Observation

In sequential execution:

Output order: Numbers printed first, then letters.

Total execution time: Around 20 seconds (each function waits for 2 seconds per iteration).

In multithreaded execution:

Output interleaves between numbers and letters. Example:

Letter: A  
Number: 0  
Number: 1  
Letter: B  
Number: 2  
Letter: C  
Number: 3  
Letter: D  
Number: 4  


Total execution time: Approximately 10 seconds (since threads overlap execution).

Key Points in Multithreading:

Thread creation using threading.Thread().

Starting threads using .start().

Ensuring completion of threads using .join().

Execution becomes concurrent, not sequential.

Useful especially when tasks involve I/O operations or when concurrent execution is required.

**(iii) Multiprocessing Practical Implementation With Python**

This section explains multiprocessing, its use cases, and implementation in Python.

Overview of Multiprocessing

Multiprocessing allows the creation of processes that run in parallel.

Each process executes independently with its own memory space.

Multiprocessing is particularly useful for CPU-bound tasks and tasks that require parallel execution across multiple cores.

When to Use Multiprocessing

a) CPU-Bound Tasks

Tasks that are computationally heavy and utilize high CPU resources.

Examples: Mathematical computations, data processing, numerical computations.

b) Parallel Execution Across CPU Cores

Useful to utilize all cores of a CPU efficiently.

Each core executes a separate process, maximizing throughput.

Implementation in Python

Import required libraries:

import multiprocessing
import time


Define functions for execution in separate processes:

def square_numbers():
    for i in range(5):
        time.sleep(1)  # Simulating heavy CPU or I/O task
        print(f"Square: {i * i}")

def cube_numbers():
    for i in range(5):
        time.sleep(1.5)  # Simulating heavy CPU or I/O task
        print(f"Cube: {i * i * i}")


Create process objects and assign target functions:

p1 = multiprocessing.Process(target=square_numbers)
p2 = multiprocessing.Process(target=cube_numbers)


Start the processes:

p1.start()
p2.start()


Wait for processes to complete using .join():

p1.join()
p2.join()


Optional: Measure execution time:

t_start = time.time()

# start processes here

t_end = time.time()
print(f"Total execution time: {t_end - t_start} seconds")

Important Notes on Multiprocessing

Unlike threads, processes have separate memory spaces, so changes in one process do not affect another.

Multiprocessing is ideal for CPU-intensive operations, whereas multithreading is more suited for I/O-bound operations.

Execution of processes runs truly in parallel (subject to number of CPU cores).

Example Observation

Output shows interleaved execution of square and cube calculations, indicating parallel execution.

Execution time is significantly reduced compared to sequential execution.

Each function runs in its independent process, visible in the Task Manager as separate Python processes.

Entry Point Requirement

The code must be protected by the if __name__ == "__main__": block when using multiprocessing in Python, especially on Windows:

if __name__ == "__main__":
    # code to start processes


This ensures the proper creation of child processes and prevents infinite recursion.

Key Points in Multiprocessing

Process creation: multiprocessing.Process(target=function)

Start process: .start()

Wait for completion: .join()

Independent memory space for each process

Best suited for CPU-heavy computations and parallelization across cores

**(iv) Thread Pool Executor and Process Pool**

This section explains advanced techniques for managing threads and processes in Python using ThreadPoolExecutor and ProcessPoolExecutor from the concurrent.futures module.

a). ThreadPoolExecutor for Multithreading

Overview:

ThreadPoolExecutor allows you to manage multiple threads efficiently.

It abstracts thread creation and management, making it easier to execute tasks concurrently.

Particularly useful for I/O-bound tasks.

Implementation Steps:

a) Import libraries:

from concurrent.futures import ThreadPoolExecutor
import time


b) Define a function for threaded execution:

def print_number(number):
    time.sleep(1)  # Simulating a delay (I/O or waiting)
    return f"Number: {number}"


c) Create a list of tasks:

numbers = [1, 2, 3, 4, 5]


d) Initialize ThreadPoolExecutor and execute tasks:

with ThreadPoolExecutor(max_workers=3) as executor:
    results = executor.map(print_number, numbers)

for result in results:
    print(result)


Key Points:

max_workers defines the maximum number of threads to run concurrently.

executor.map applies the function to all items in the list.

Threads execute concurrently, so tasks complete much faster than sequential execution even with delays.

Works for larger lists and can be scaled by increasing the number of threads.

b). ProcessPoolExecutor for Multiprocessing

Overview:

ProcessPoolExecutor allows you to manage multiple processes efficiently.

Suitable for CPU-bound tasks, where each process runs in parallel across CPU cores.

Each process has its own memory space.

Implementation Steps:

a) Import libraries:

from concurrent.futures import ProcessPoolExecutor
import time


b) Define a CPU-bound function:

def square(number):
    time.sleep(1)  # Simulating heavy computation
    return number * number


c) Create a list of tasks:

numbers = [1, 2, 3, 4, 5]


d) Use ProcessPoolExecutor to run tasks in parallel:

if __name__ == "__main__":
    with ProcessPoolExecutor(max_workers=3) as executor:
        results = executor.map(square, numbers)
    for result in results:
        print(result)


Key Points:

max_workers defines the number of processes.

Tasks are distributed across CPU cores, executing truly in parallel.

The if __name__ == "__main__": block is mandatory for multiprocessing in Python, especially on Windows, to avoid errors like “process in the pool was terminated while the future was running or pending.”

Allows for fast execution of CPU-intensive computations even with delays or heavy calculations.

c). Observations and Advantages

Both ThreadPoolExecutor and ProcessPoolExecutor simplify managing threads and processes.

Execution time is significantly reduced compared to sequential execution.

ThreadPoolExecutor is ideal for I/O-bound tasks, while ProcessPoolExecutor is ideal for CPU-bound tasks.

Both executors allow you to work with large datasets and multiple tasks concurrently, without manually creating threads or processes.

Time delays (e.g., time.sleep) do not block other threads or processes, enabling efficient concurrent execution.

Summary
Feature	ThreadPoolExecutor	ProcessPoolExecutor
Type	Threads (I/O-bound)	Processes (CPU-bound)
Memory	Shared memory	Separate memory for each process
Use case	Waiting for I/O operations	Heavy computations or CPU-intensive tasks
Implementation	ThreadPoolExecutor(max_workers=...)	ProcessPoolExecutor(max_workers=...)
Entry Point Requirement	Not required	if __name__ == "__main__": mandatory

Conclusion:

ThreadPoolExecutor and ProcessPoolExecutor provide advanced, efficient concurrency management.

These techniques allow Python applications to handle multiple tasks faster and more efficiently.

Thread pool and process pool executors are essential for building scalable applications with multithreading or multiprocessing.

**(v) Implement Web Scraping Usecase With Multithreading**

This video explains implementing multithreading for I/O-bound tasks using a real-world example of web scraping.

a). Problem Statement

Web scraping involves making multiple network requests to fetch web pages.

These tasks are I/O-bound because they spend a lot of time waiting for server responses.

Multithreading can improve performance by fetching multiple web pages concurrently.

For each URL, a separate thread can be created to retrieve content in parallel, reducing total execution time.

Example Scenario:

The video uses three URLs for demonstration.

Goal: Count the number of characters on each web page using multithreading.

b). Required Libraries

threading → To create and manage threads.

requests → To make HTTP requests to fetch web pages.

bs4 (BeautifulSoup) → To parse HTML content.

Installation of BeautifulSoup:

pip install -r requirements.txt


Import statements in code:

import threading
import requests
from bs4 import BeautifulSoup

c). Web Scraping Function

Function Definition:

def fetch_contents(url):
    response = requests.get(url)  # Make HTTP GET request
    soup = BeautifulSoup(response.content, "html.parser")  # Parse HTML content
    print(f"Fetched {len(soup.text)} characters from {url}")


Explanation:

requests.get(url) fetches the HTML content of the URL.

BeautifulSoup(response.content, "html.parser") parses the HTML.

Instead of printing entire HTML content, the length of the text is printed for simplicity.

d). Creating Threads

Steps to create and start threads for each URL:

threads = []

for url in urls:
    t = threading.Thread(target=fetch_contents, args=(url,))
    threads.append(t)
    t.start()


For each URL in the list, a thread is created targeting fetch_contents.

args=(url,) passes the URL to the function.

Each thread is started immediately using t.start().

Wait for all threads to finish:

for thread in threads:
    thread.join()


Ensures that the main program waits until all threads have completed execution.

e). Execution

When executed, all three threads fetch content concurrently.

Example Output:

Fetched 7477 characters from URL1
Fetched 8986 characters from URL2
Fetched 66004044 characters from URL3


Observation:

Threads are running in parallel.

Each thread fetches the content independently and prints the number of characters.

Execution time is significantly reduced compared to sequential fetching.

f). Key Points

Multithreading is ideal for I/O-bound tasks like web scraping.

Each URL can have a dedicated thread, allowing parallel execution.

Threading reduces waiting time for server responses.

Number of threads can be scaled based on the number of URLs.

Even if one thread takes longer, others continue executing concurrently.

Summary

Task Type: I/O-bound (web scraping).

Technique: Multithreading using threading.Thread.

Advantage: Multiple pages fetched concurrently, reducing total execution time.

Implementation Steps:

a) Import threading, requests, BeautifulSoup.

b) Define a function to fetch content and process it.

c) Create threads for each URL and start them.

d) Join threads to wait for completion.

e) Print results (e.g., number of characters).

Conclusion:

Multithreading allows efficient concurrent execution of I/O-bound tasks.

Web scraping with multiple URLs demonstrates a practical real-world use case.

Threads work independently and fetch results simultaneously, improving performance.

**(vi) Real World Usecase Implementation With MultiProcessing**

This video explains using multiprocessing for CPU-bound tasks with a practical example of calculating factorials of large numbers.

a). Problem Statement

CPU-bound tasks involve intensive computations that fully utilize CPU resources.

Calculating factorials of large numbers is computationally heavy.

Using a single core would leave other CPU cores idle and take a very long time.

Multiprocessing allows distributing the workload across multiple CPU cores to improve performance.

Example Scenario:

Compute factorials for a list of large numbers.

Each factorial computation is heavy, making this an ideal CPU-bound use case.

b). Required Libraries

multiprocessing → To create and manage multiple processes.

math → To use the built-in factorial function.

sys → To increase the maximum number of digits Python can handle for large integers.

time → To measure execution time.

Import statements in code:

import multiprocessing
import math
import sys
import time


Set maximum integer digits:

sys.set_int_max_str_digits(100000)  # Allow up to 100,000 digits

c). Factorial Function

Function Definition:

def compute_factorial(number):
    print(f"Computing factorial of {number}")
    result = math.factorial(number)  # Compute factorial using math module
    print(f"Factorial of {number} computed")
    return result


Explanation:

number is passed as an argument.

The function computes the factorial using math.factorial().

Prints the start and end of computation for clarity.

Returns the computed factorial.

d). Multiprocessing Implementation

Steps:

a) Create the entry point:

if __name__ == "__main__":


b) Define the list of numbers:

numbers = [6000, 7000, 8000]  # Large numbers for factorial computation


c) Start timer:

start_time = time.time()


d) Create a pool of worker processes:

with multiprocessing.Pool() as pool:
    results = pool.map(compute_factorial, numbers)


multiprocessing.Pool() creates a pool of processes.

pool.map() applies the compute_factorial function to each number in parallel across multiple CPU cores.

This utilizes all available cores efficiently.

e) End timer and print results:

end_time = time.time()
print(results)
print(f"Time taken: {end_time - start_time} seconds")


Displays the factorial results.

Shows the total time taken for computation.

e). Execution

On execution, all CPU cores are utilized simultaneously.

Example Output:

Computing factorial of 6000
Computing factorial of 7000
Computing factorial of 8000
[<factorial_6000>, <factorial_7000>, <factorial_8000>]
Time taken: 4.4375 seconds


Observation:

Without multiprocessing (using a single core), the system may hang or take much longer.

Using pool.map() with multiple processes drastically reduces execution time.

Works efficiently even for very large numbers.

f). Key Points

Factorial calculation of large numbers is a CPU-bound task.

Multiprocessing distributes computation across multiple CPU cores.

Using a process pool is more efficient than sequential execution.

pool.map() allows applying a function to multiple inputs in parallel.

Increasing sys.set_int_max_str_digits() ensures Python can handle large factorials without errors.

Summary

Task Type: CPU-bound (factorial computation).

Technique: Multiprocessing using multiprocessing.Pool.

Advantages:

Utilizes all CPU cores.

Reduces computation time drastically.

Handles large numbers efficiently.

Implementation Steps:

a) Import required libraries (multiprocessing, math, sys, time).

b) Set max integer digits for large numbers.

c) Define a factorial computation function.

d) Create a process pool and map the function to the list of numbers.

e) Measure and print execution time and results.

Conclusion:

Multiprocessing is essential for CPU-intensive tasks.

Using a process pool for factorial computation demonstrates a practical real-world use case for CPU-bound operations.

This method ensures efficient parallel execution and optimal CPU utilization.

**52. Logging in Python:**

**Logging is a crucial aspect of any application, providing a way to track events, errors, and operational information. Python's built-in logging module offers a flexible framework for emitting log messages from Python programs.**

import logging

## Configure the basic logging settings
logging.basicConfig(level=logging.DEBUG)

## log messages with different severity levels
logging.debug("This is a debug message")
logging.info("This is an info message")
logging.warning("This is a warning message")
logging.error("This is an error message")
logging.critical("This is a critical message")

#### Log Levels
Python's logging module has several log levels indicating the severity of events. The default levels are:

- DEBUG: Detailed information, typically of interest only when diagnosing problems.
- INFO: Confirmation that things are working as expected.
- WARNING: An indication that something unexpected happened or indicative of some problem in the near future (e.g., ‘disk space low’). The software is still working as expected.
- ERROR: Due to a more serious problem, the software has not been able to perform some function.
- CRITICAL: A very serious error, indicating that the program itself may be unable to continue running.

  ## configuring logging
import logging

**Creates a Log File called app.log file in VS Code**

**Once we configured the BASICCONFIG, unless we restart the Kernel, it won't change (Since it would have already been created)**

**Once we have done the Configuration for the Logs, we can use anywhere**

logging.basicConfig(
    filename='app.log',
    filemode='w',
    level=logging.DEBUG,
    format='%(asctime)s-%(name)s-%(levelname)s-%(message)s',
    datefmt='%Y-%m-%d %H:%M:%S'
    )

## log messages with different severity levels
logging.debug("This is a debug message")
logging.info("This is an info message")
logging.warning("This is a warning message")
logging.error("This is an error message")
logging.critical("This is a critical message")

# **54. Memory Management With Python**

**(i) Memory Allocation And Deallocation Garbage collection and Best Practises**

This video explains how Python manages memory automatically, how developers can leverage reference counting, garbage collection, and best practices to write efficient and robust applications.

a). Overview

Memory management in Python involves:

Automatic garbage collection

Reference counting

Internal optimizations for efficient memory allocation/deallocation

Understanding these mechanisms helps write optimized and robust code.

b). Reference Counting

Definition: Python objects maintain a count of references pointing to them.

When the reference count drops to zero, the memory occupied by the object is automatically deallocated.

Example using sys.getrefcount():

import sys

a = [1, 2, 3]
print(sys.getrefcount(a))  # Output: 2


Output is 2 because:

a refers to the list.

getrefcount() temporarily adds another reference.

Adding another reference:

b = a
print(sys.getrefcount(a))  # Output: 3


When b is deleted:

del b
print(sys.getrefcount(a))  # Output: 2


Key Point:

Python automatically deallocates objects once the reference count is zero.

c). Garbage Collection (GC)

Garbage collection handles memory cleanup, including circular references (where objects reference each other).

Uses the GC module in Python.

Basic operations:

import gc

gc.enable()    # Enable garbage collection
gc.disable()   # Disable garbage collection
gc.collect()   # Manually trigger garbage collection


gc.collect() returns the number of unreachable objects collected.

gc.get_stats() gives per-generation collection statistics.

gc.garbage lists uncollectable objects.

Circular Reference Example:

class MyObject:
    def __init__(self, name):
        self.name = name
        print(f"Object {name} created")
    def __del__(self):
        print(f"Object {self.name} deleted")

obj1 = MyObject("obj1")
obj2 = MyObject("obj2")

obj1.reference = obj2
obj2.reference = obj1

del obj1
del obj2

gc.collect()  # Required to delete objects due to circular reference


Observation: Circular references prevent automatic deletion; gc.collect() is needed.

d). Best Practices for Memory Management

a) Use local variables:

Local variables have a shorter lifespan and are freed sooner than global variables.

b) Avoid circular references:

Circular references can cause memory leaks.

c) Use generators:

Generate items one at a time using yield to keep only one item in memory.

Generator Example:

def generate_numbers(n):
    for i in range(n):
        yield i

for num in generate_numbers(100):
    print(num)
    if num > 10:
        break


d) Explicitly delete objects:

Use del keyword for objects no longer needed.

e) Profile memory usage:

Use tools like tracemalloc to identify memory usage and leaks.

Memory Profiling Example:

import tracemalloc

def create_list(n):
    return [i for i in range(n)]

def main():
    tracemalloc.start()
    create_list(1000)
    snapshot = tracemalloc.take_snapshot()
    top_stats = snapshot.statistics('lineno')
    for stat in top_stats[:10]:
        print(stat)

main()


Shows top memory-consuming lines and objects.

e). Summary

Reference counting: Automatically tracks object references.

Garbage collection: Cleans up unreachable objects and resolves circular references.

Generators: Efficient memory usage for large datasets.

Memory profiling: Identify memory leaks and optimize usage.

Best practices: Use local variables, avoid circular references, delete unused objects, use generators, profile memory.

Conclusion:

Python handles most memory management automatically.

Manual intervention (e.g., gc.collect(), del) is sometimes needed for circular references or optimization.

Understanding these concepts helps in building efficient, high-performance Python applications.
