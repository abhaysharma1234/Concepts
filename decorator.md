# Decorators in Python

## 1. Introduction

Python supports higher-order programming concepts, and decorators are one of the most practical applications of this capability.

A decorator is a callable that:

- Accepts another function as input  
- Extends or modifies its behavior  
- Returns a new function  

Instead of modifying the original function directly, decorators wrap additional functionality around it. This promotes cleaner architecture and better separation of concerns.

---

## 2. Functions as First-Class Objects

Decorators are possible because Python treats functions as first-class objects. This means:

- Functions can be assigned to variables  
- Functions can be passed as arguments  
- Functions can return other functions  

### Example

```python
def greet():
    return "Hello"

message = greet
print(message())
```

This flexibility forms the foundation of decorators.

---

## 3. Basic Structure of a Decorator

A decorator consists of:

1. An outer function (decorator)
2. An inner function (wrapper)
3. Returning the wrapper function

### Example

```python
def decorator_function(original_function):
    def wrapper():
        print("Executing before the function")
        original_function()
        print("Executing after the function")
    return wrapper

@decorator_function
def display():
    print("Inside the function")

display()
```

### Equivalent Form

```python
display = decorator_function(display)
```

The original function is replaced with the enhanced wrapper function.

---

## 4. Decorators with Arguments

When the decorated function accepts parameters, use `*args` and `**kwargs`.

### Example

```python
def decorator_function(original_function):
    def wrapper(*args, **kwargs):
        print("Function execution started")
        result = original_function(*args, **kwargs)
        print("Function execution completed")
        return result
    return wrapper

@decorator_function
def multiply(a, b):
    return a * b

print(multiply(4, 5))
```

This allows the decorator to handle any number of arguments.

---

## 5. Execution Time Decorator Example

```python
import time

def timer(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print("Execution time:", end - start)
        return result
    return wrapper

@timer
def slow_function():
    time.sleep(2)
    print("Task completed")

slow_function()
```

---

## 6. Logging Decorator Example

```python
def logger(func):
    def wrapper(*args, **kwargs):
        print(f"Calling function: {func.__name__}")
        return func(*args, **kwargs)
    return wrapper

@logger
def add(a, b):
    return a + b

print(add(3, 7))
```

---

## 7. Using functools.wraps

To preserve metadata of the original function:

```python
from functools import wraps

def decorator(func):
    @wraps(func)
    def wrapper(*args, **kwargs):
        print("Running function")
        return func(*args, **kwargs)
    return wrapper

@decorator
def sample():
    """Sample function"""
    pass

print(sample.__name__)
print(sample.__doc__)
```

---

## 8. Multiple Decorators

```python
def decorator1(func):
    def wrapper(*args, **kwargs):
        print("Decorator 1")
        return func(*args, **kwargs)
    return wrapper

def decorator2(func):
    def wrapper(*args, **kwargs):
        print("Decorator 2")
        return func(*args, **kwargs)
    return wrapper

@decorator1
@decorator2
def test():
    print("Inside function")

test()
```

Execution order:

```
Decorator 1
Decorator 2
Inside function
```

---

## 9. Built-in Python Decorators

Python provides built-in decorators commonly used in object-oriented programming:

- `@staticmethod`
- `@classmethod`
- `@property`

### Example

```python
class Example:
    @staticmethod
    def greet():
        return "Hello"
```

---

