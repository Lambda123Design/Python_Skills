# Python_Skills

Following are my Python Skills:

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

48. **Python for Data Analysis:**

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
   

   49. Read Data from Various Sources:

df=pd.read_json(StringIO(Data)), df.to_json(orient='index'), df=pd.read_csv(),df.to_csv(), df=pd.read_html(url) (Need 3 Libraries - 'lxml, html5lib, beautifulsoup4'), pd.read_html(url,match="Country",header=0)[0], pd.read_excel  (Need openpyxl), df_excel.to_pickle(), pd.read_pickle(), 
