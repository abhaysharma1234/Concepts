# SOLID Principles in Python

## 1. What is SOLID?

**SOLID** is a set of **five design principles** that help in writing:

* Clean code
* Maintainable code
* Scalable software
* Easy-to-test applications

**SOLID stands for:**

* **S** → Single Responsibility Principle
* **O** → Open/Closed Principle
* **L** → Liskov Substitution Principle
* **I** → Interface Segregation Principle
* **D** → Dependency Inversion Principle

---

# 2. Single Responsibility Principle (SRP)

### Definition

A **class should have only one reason to change**
→ meaning **one job only**.

### Bad Example

```python
class Report:
    def generate(self):
        print("Generating report")

    def save_to_file(self):
        print("Saving to file")
```

Problem:
This class has **two responsibilities** → generating + saving.

---

### Good Example

```python
class ReportGenerator:
    def generate(self):
        print("Generating report")


class ReportSaver:
    def save(self):
        print("Saving report to file")


gen = ReportGenerator()
gen.generate()

saver = ReportSaver()
saver.save()
```

**Output**

```
Generating report
Saving report to file
```

 Each class has **one responsibility**.

---

# 3. Open/Closed Principle (OCP)

### Definition

Software should be:

* **Open for extension**
* **Closed for modification**

→ Add new behavior **without changing old code**.

---

### Bad Example

```python
class Discount:
    def calculate(self, customer_type, amount):
        if customer_type == "regular":
            return amount * 0.9
        elif customer_type == "vip":
            return amount * 0.8
```

Problem:
Adding a new customer → **modify existing code**.

---

### Good Example

```python
class Discount:
    def calculate(self, amount):
        return amount


class RegularDiscount(Discount):
    def calculate(self, amount):
        return amount * 0.9


class VIPDiscount(Discount):
    def calculate(self, amount):
        return amount * 0.8


for d in (RegularDiscount(), VIPDiscount()):
    print(d.calculate(100))
```

**Output**

```
90.0
80.0
```

 New discount types can be **added without editing old classes**.

---

# 4. Liskov Substitution Principle (LSP)

### Definition

A **child class must be usable** in place of its **parent class**
without breaking the program.

---

### Bad Example

```python
class Bird:
    def fly(self):
        print("Flying")


class Penguin(Bird):
    def fly(self):
        raise Exception("Penguins can't fly")
```

Problem:
`Penguin` **cannot replace** `Bird`.

---

### Good Example

```python
class Bird:
    pass


class FlyingBird(Bird):
    def fly(self):
        print("Flying")


class Penguin(Bird):
    def swim(self):
        print("Swimming")


fb = FlyingBird()
fb.fly()

p = Penguin()
p.swim()
```

**Output**

```
Flying
Swimming
```

 Subclasses behave **correctly**.

---

# 5. Interface Segregation Principle (ISP)

### Definition

**Do not force a class to implement methods it doesn't use.**
→ Prefer **small, specific interfaces**.

---

### Bad Example

```python
class Worker:
    def work(self): pass
    def eat(self): pass
```

Robot **doesn't need** `eat()` → bad design.

---

### Good Example

```python
class Workable:
    def work(self):
        pass


class Eatable:
    def eat(self):
        pass


class Human(Workable, Eatable):
    def work(self):
        print("Human working")

    def eat(self):
        print("Human eating")


class Robot(Workable):
    def work(self):
        print("Robot working")


Human().eat()
Robot().work()
```

**Output**

```
Human eating
Robot working
```

 Classes implement **only what they need**.

---

# 6. Dependency Inversion Principle (DIP)

### Definition

* High-level modules **should not depend on low-level modules**
* Both should depend on **abstractions**

---

### Bad Example

```python
class Keyboard:
    def type(self):
        print("Typing...")


class Computer:
    def __init__(self):
        self.keyboard = Keyboard()
```

Problem:
`Computer` **directly depends** on `Keyboard`.

---

### Good Example

```python
class InputDevice:
    def type(self):
        pass


class Keyboard(InputDevice):
    def type(self):
        print("Typing with keyboard")


class Computer:
    def __init__(self, device: InputDevice):
        self.device = device

    def input(self):
        self.device.type()


c = Computer(Keyboard())
c.input()
```

**Output**

```
Typing with keyboard
```

Now we can plug **any input device** without changing `Computer`.

---

# 7. Advantages of SOLID

* Cleaner architecture
* Easier testing
* Better scalability
* Reduced bugs
* Faster development in large projects

---

