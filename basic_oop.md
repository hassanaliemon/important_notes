

---

## The Pillars of OOP:

1. **Encapsulation:**
   Encapsulation refers to the bundling of data and methods together within a class. It involves hiding the internal details of an object and providing a public interface to interact with the object. Encapsulation helps in achieving data abstraction, data integrity, and code modularity.

2. **Inheritance:**
   Inheritance allows the creation of a new class (derived or child class) based on an existing class (base or parent class). The derived class inherits attributes and methods from the base class, enabling code reuse and the establishment of an "is-a" relationship between classes. Inheritance promotes code extensibility and hierarchical organization of classes.

3. **Polymorphism:**
   Polymorphism means the ability of objects to take on different forms or respond in different ways based on the context. It allows objects of different classes to be treated as objects of a common superclass. Polymorphism is achieved through method overriding and method overloading, enabling dynamic method dispatch and flexibility in implementing different behaviors.

4. **Abstraction:**
   Abstraction involves simplifying complex systems by focusing on essential features while hiding unnecessary details. It provides a conceptual model that captures the essential characteristics of an object, without exposing the implementation details. Abstraction helps in managing complexity, improving code maintainability, and facilitating code reuse.

---

These pillars provide the foundation for building modular, extensible, and maintainable software systems using OOP principles. They allow for better organization of code, reusability, and flexibility in designing and implementing complex systems.

## Differencce between Abstraction and Encapsulation

https://www.upgrad.com/blog/abstraction-vs-encapsulation/

### What is data abstraction?
Data abstraction is a very important feature of OOPs that allows displaying only the important information and hiding the implementation details.
### How to achieve data abstraction?
Data abstraction can be achieved through:
1. Abstract class
2. Abstract method

### What is an abstract class?
An abstract class in object-oriented programming is a class that cannot be instantiated directly and is meant to serve as a blueprint for its subclasses. It is designed to be inherited by other classes, which then provide specific implementations for its abstract methods.

An abstract class typically contains one or more abstract methods, which are declared but not implemented in the abstract class itself. The responsibility of implementing these abstract methods is left to the subclasses. The abstract class may also contain regular methods with defined behavior that can be inherited by its subclasses.

The main purpose of an abstract class is to define a common interface or contract for its subclasses. It establishes a set of methods that the subclasses must implement, ensuring that they adhere to a certain structure and functionality. This allows for the creation of a family of related classes that share common characteristics and behaviors.

In many programming languages, including Python, abstract classes are usually implemented using abstract base classes (ABCs). In Python, you can create an abstract class by inheriting from the abc.ABC class or by using the @abc.abstractmethod decorator to mark methods as abstract.

### Can you create an instance of an abstract class?
No. Instances of an abstract class cannot be created because it does not have a complete implementation. However, instances of subclass inheriting the abstract class can be created.

### What is access specifier
In Python, there are no explicit access specifiers like in some other programming languages such as C++ (e.g., private, protected, public). However, Python uses a convention to indicate the visibility of class members, such as attributes and methods.
```python
class MyClass:
    def __init__(self):
        self.public_var = 10
        self._protected_var = 20
        self.__private_var = 30
```


## Polymorphism

https://www.upgrad.com/blog/polymorphism-in-oops/

### What is static polymorphism?
Static polymorphism (static binding) is a kind of polymorphism that occurs at compile time. An example of compile-time polymorphism is method overloading.

### What is dynamic polymorphism?
Runtime polymorphism or dynamic polymorphism (dynamic binding) is a type of polymorphism which is resolved during runtime. An example of runtime polymorphism is method overriding.

### What is method overloading?
Method overloading is a feature of OOPs which makes it possible to give the same name to more than one methods within a class if the arguments passed differ.

### What is method overriding?
Method overriding is a feature of OOPs by which the child class or the subclass can redefine methods present in the base class or parent class. Here, the method that is overridden has the same name as well as the signature meaning the arguments passed and the return type.

### what is virtual function

In object-oriented programming, a virtual function is a function that is declared in a base class and is intended to be overridden by derived classes. The concept of virtual functions is closely related to polymorphism, which allows objects of different classes to be treated as objects of a common base class.
    
By default, in Python, all functions are virtual by default, meaning they can be overridden in derived classes without any specific keyword or declaration. Unlike languages like C++, there is no need to explicitly mark a function as virtual.
### What are pure virtual functions?
Pure virtual functions or abstract functions are functions that are only declared in the base class. This means that they do not contain any definition in the base class and need to be redefined in the subclass.

## Inheritance

### What are the different types of inheritance?
1. Single inheritance
2. Multiple inheritance
3. Multilevel inheritance
4. Hierarchical inheritance
5. Hybrid inheritance

### What is hierarchical inheritance?

Hierarchical inheritance is a type of inheritance in object-oriented programming where a single base class is inherited by multiple derived classes. In this inheritance hierarchy, each derived class serves as a base class for its own set of further derived classes, forming a hierarchical structure.

The hierarchical inheritance structure can be visualized as a tree-like structure, where the base class is at the root, and the derived classes branch out from it. Each derived class inherits all the properties and behaviors of the base class, and can also add its own unique properties and behaviors.

## Hierarchical Inheritance Example

Consider a scenario where we have a base class called `Animal`:

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def eat(self):
        print(f"{self.name} is eating.")
```
From the Animal class, we can derive two specialized classes: Cat and Dog. Both Cat and Dog inherit from Animal and add their own unique behaviors:
```python
class Cat(Animal):
    def meow(self):
        print(f"{self.name} is meowing.")

class Dog(Animal):
    def bark(self):
        print(f"{self.name} is barking.")
```
### What is hybrid inheritance?
Hybrid inheritance is a combination of multiple and multi-level inheritance.

### What are the limitations of inheritance?
1. Increases the time and effort required to execute a program as it requires jumping back and forth between different classes
2. The parent class and the child class get tightly coupled
Any modifications to the program would require changes both in the parent as well as the child class
3. Needs careful implementation else would lead to incorrect results

---

### difference between static, class and instance method
**Instance Methods:**
1. Instance methods are the most common type of methods in Python classes.
2. They are bound to an instance of a class and can access and modify the instance's attributes.
3. Instance methods have access to the self parameter, which represents the instance itself.
4. They are typically used to perform actions specific to individual instances of a class.

**Class Methods:**
1. Class methods are defined with the @classmethod decorator and operate on the class itself rather than instances of the class.
2. They have access to the class itself via the cls parameter, which is automatically passed as the first argument.
3. Class methods are commonly used to create alternative constructors or perform operations that involve the class as a whole.
4. They can't access or modify instance-specific attributes directly, but they can work with class-level attributes.

**Static Methods:**
1. Static methodsare defined with the @staticmethod decorator and don't require a reference to the instance or the class.
2. They behave like regular functions but are defined inside a class for organizational purposes.
3. Static methods can't access or modify instance or class attributes directly because they don't have access to the self or cls parameters.
4. They are commonly used when a method doesn't depend on the state of the instance or class.

```python
class MyClass:
    class_attribute = "Class Attribute"

    def __init__(self, instance_attribute):
        self.instance_attribute = instance_attribute

    def instance_method(self):
        print("Instance Method")
        print(f"Accessing instance attribute: {self.instance_attribute}")
        print(f"Accessing class attribute: {self.class_attribute}")

    @classmethod
    def class_method(cls):
        print("Class Method")
        print(f"Accessing class attribute: {cls.class_attribute}")

    @staticmethod
    def static_method():
        print("Static Method")

# Creating an instance of MyClass
my_instance = MyClass("Instance Attribute")

# Calling instance method
my_instance.instance_method()

# Calling class method
MyClass.class_method()

# Calling static method
MyClass.static_method()
```

N.B: Class doesn't need to instantiated to access class method but has to instantiate to access instance methods

## Abstract method
An abstract method is a method that has a declaration but does not have an implementation. While we are designing large functional units, we use an abstract class. An abstract class can be considered as a blueprint for other classes.

In Python Abstract class doesn’t have straight foreward implementation, We need to import abc(abstract base class). ABC works by decorating the base class’s methods as abstract and then registering concrete classes as implementations of the conceptual base.
```python
from abc import ABC, abstractmethod
class POLYGON(ABC):
    @abstractmethod
    def number_of_sides(self):
        pass
class RECTANGLE(POLYGON):

    def number_of_sides(self):
        print(“I have 2 sides”)
```
1. Abstract methods are created using the @abstractmethod decorator.
2. They override the properties of base class.

## @property decorator 
The @property decorator in Python is used to define a method as a property. It allows you to access a method like an attribute, providing a convenient way to encapsulate the access and modification of class attributes.

When you use the @property decorator, you define a method that acts as a getter for a specific attribute. This method is called when you access the attribute, and you can perform custom logic or calculations before returning the value. The @property decorator transforms the method into a read-only attribute.

Here's an example to illustrate the usage of @property decorator:
```python
class Circle:
    def __init__(self, radius):
        self.radius = radius
    @property
    def area(self):
        return 3.14 * self.radius**2

# Create an instance of Circle
my_circle = Circle(5)
# Access the area attribute like an attribute, not a method
print(my_circle.area)
```
