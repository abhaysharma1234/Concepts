# PEP 8 Style

## Introduction

PEP 8 (Python Enhancement Proposal 8) defines the official style guidelines for writing Python code. It promotes readability, consistency, and maintainability across Python projects. This document summarizes the core rules and best practices defined in PEP 8.

---

## 1. Overview

PEP 8 provides conventions for:

- Code layout  
- Naming standards  
- Indentation  
- Imports  
- Whitespace usage  
- Comments and documentation  

The primary objective is improving **code readability** and **uniformity**.

---

## 2. Importance of PEP 8

Following PEP 8 ensures:

- Clean and structured code  
- Easier debugging  
- Better team collaboration  
- Reduced maintenance cost  
- Consistent coding standards  

> "Readability counts." — Zen of Python

---

## 3. Naming Conventions

### 3.1 Variables and Functions

- Use lowercase letters  
- Separate words with underscores  
- Follow `snake_case` format  

```python
total_count = 10

def calculate_sum(a, b):
    return a + b
```

---

### 3.2 Classes

- Use `PascalCase` (CapitalizedWords)

```python
class StudentDetails:
    pass
```

---

### 3.3 Constants

- Use uppercase letters  
- Separate words with underscores  

```python
MAX_LIMIT = 100
DEFAULT_TIMEOUT = 30
```

---

## 4. Indentation Rules

- Use **4 spaces per indentation level**
- Do not use tabs
- Maintain consistent indentation throughout the file

```python
def greet(name):
    if name:
        print("Hello", name)
```

---

## 5. Line Length Guidelines

- Maximum line length: **79 characters**
- Comments and docstrings: **72 characters**
- Break long expressions properly

```python
total = (first_value + second_value +
         third_value + fourth_value)
```

---

## 6. Blank Line Usage

- Use **2 blank lines** before top-level functions and classes  
- Use **1 blank line** inside class methods  
- Avoid excessive spacing  

---

## 7. Import Formatting

### Rules:

- Place imports at the top of the file  
- One import per line  
- Group imports in the following order:

1. Standard library  
2. Third-party libraries  
3. Local modules  

```python
import os
import sys

import numpy as np

from mymodule import my_function
```

---

## 8. Whitespace Guidelines

### Correct Usage

- Use single space around operators  

```python
x = a + b
```

- Avoid extra spaces inside brackets  

```python
numbers = [1, 2, 3]
```

- Avoid trailing whitespace  

---

## 9. Comments and Docstrings

### Comments

- Use clear and meaningful explanations  
- Keep them concise and updated  

```python
# Calculate total price including tax
total_price = price * 1.18
```

---

### Docstrings

- Use triple quotes  
- Describe purpose, parameters, and return value  

```python
def add(a, b):
    """
    Returns the sum of two numbers.
    """
    return a + b
```

---

