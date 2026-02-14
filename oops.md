# Object Oriented Programming (OOP) in Python

## 1. What is OOP?

**Object Oriented Programming (OOP)** is a programming paradigm based on:

* **Objects** → real-world entities with data and behavior
* **Classes** → blueprints used to create objects

OOP helps in:

* Code reusability
* Better structure
* Easy maintenance
* Scalability

---

## 2. Class and Object

### Class

A **class** is a blueprint for creating objects.

### Object

An **object** is an instance of a class.

```python
class Student:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display(self):
        print(self.name, self.age)


s1 = Student("Abhay", 21)
s1.display()
```

**Output**

```
Abhay 21
```

---

## 3. Constructor (`__init__`)

* Runs automatically when object is created
* Used to initialize variables

```python
class Car:
    def __init__(self, brand):
        self.brand = brand

c = Car("BMW")
print(c.brand)
```

**Output**

```
BMW
```

---

## 4. Instance Variables vs Methods

```python
class Person:
    def __init__(self, name):
        self.name = name      # instance variable

    def greet(self):          # instance method
        print("Hello", self.name)


p = Person("Abhay")
p.greet()
```

**Output**

```
Hello Abhay
```

---

## 5. Four Pillars of OOP

### 5.1 Encapsulation

* Wrapping **data + methods** together
* Restrict direct access using **private variables**

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance   # private variable

    def deposit(self, amount):
        self.__balance += amount

    def get_balance(self):
        return self.__balance


acc = BankAccount(1000)
acc.deposit(500)
print(acc.get_balance())
```

**Output**

```
1500
```

---

### 5.2 Inheritance

* One class **inherits** properties of another

```python
class Animal:
    def speak(self):
        print("Animal speaks")


class Dog(Animal):
    def bark(self):
        print("Dog barks")


d = Dog()
d.speak()
d.bark()
```

**Output**

```
Animal speaks
Dog barks
```

---

### 5.3 Polymorphism

* **Same method name**, different behavior

```python
class Cat:
    def sound(self):
        print("Meow")


class Dog:
    def sound(self):
        print("Bark")


for animal in (Cat(), Dog()):
    animal.sound()
```

**Output**

```
Meow
Bark
```

---

### 5.4 Abstraction

* Hiding **implementation details**
* Showing only **essential features**

```python
from abc import ABC, abstractmethod

class Shape(ABC):

    @abstractmethod
    def area(self):
        pass


class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side * self.side


s = Square(4)
print(s.area())
```

**Output**

```
16
```

---

## 6. Class Variables vs Instance Variables

```python
class Employee:
    company = "TCS"   # class variable

    def __init__(self, name):
        self.name = name   # instance variable


e1 = Employee("Abhay")
e2 = Employee("Rahul")

print(e1.company)
print(e2.name)
```

**Output**

```
TCS
Rahul
```

---

## 7. Method Types in Python

### Instance Method

```python
class Demo:
    def instance_method(self):
        print("Instance method")


Demo().instance_method()
```

**Output**

```
Instance method
```

---

### Class Method

```python
class Demo:
    value = 10

    @classmethod
    def show(cls):
        print(cls.value)


Demo.show()
```

**Output**

```
10
```

---

### Static Method

```python
class Demo:
    @staticmethod
    def add(a, b):
        return a + b


print(Demo.add(2, 3))
```

**Output**

```
5
```

---

## 8. `__str__` Method (Object Representation)

```python
class Book:
    def __init__(self, title):
        self.title = title

    def __str__(self):
        return self.title


b = Book("Python Basics")
print(b)
```

**Output**

```
Python Basics
```

---

## 9. Advantages of OOP

* Reusable code
* Modular structure
* Easy debugging
* Real-world modeling
* Better security with encapsulation

---


