# Python Cheat Sheet (with Outputs)

## 1. Basic Python Concepts

### Variables

```python
x = 5
name = "Abhay"
print(x)
print(name)
```

**Output**

```
10
Abhay
```

---

### Data Types

```python
print(type(5))
print(type(1.14))
print(type("hello"))
print(type(True))
print(type([1, 2, 3]))
print(type((1, 2, 3)))
print(type({"a": 1}))
print(type({1, 2, 3}))
```

**Output**

```
<class 'int'>
<class 'float'>
<class 'str'>
<class 'bool'>
<class 'list'>
<class 'tuple'>
<class 'dict'>
<class 'set'>
```

---

### Conditional Statements

```python
age = 18

if age >= 18:
    print("Adult")
else:
    print("Child")
```

**Output**

```
Adult
```

---

### Loops

#### For loop

```python
for i in range(5):
    print(i)
```

**Output**

```
0
1
2
3
4
```

#### While loop

```python
count = 0
while count < 3:
    print(count)
    count += 1
```

**Output**

```
0
1
2
```

---

### Functions

```python
def greet(name):
    return f"Hello {name}"

print(greet("Abhay"))
```

**Output**

```
Hello Abhay
```

---

### Classes & Objects

```python
class Person:
    def __init__(self, name):
        self.name = name

    def say_hi(self):
        print("Hi,", self.name)

p = Person("Abhay")
p.say_hi()
```

**Output**

```
Hi, Abhay
```

---

## 2. Popular String Methods

### `lower()`

```python
print("HELLO".lower())
```

**Output**

```
hello
```

### `upper()`

```python
print("hello".upper())
```

**Output**

```
HELLO
```

### `strip()`

```python
print("  hi  ".strip())
```

**Output**

```
hi
```

### `replace()`

```python
print("apple".replace("a", "A"))
```

**Output**

```
Apple
```

### `split()`

```python
print("a,b,c".split(","))
```

**Output**

```
['a', 'b', 'c']
```

### `join()`

```python
print(",".join(["a", "b", "c"]))
```

**Output**

```
a,b,c
```

### `find()`

```python
print("hello".find("e"))
```

**Output**

```
1
```

### `count()`

```python
print("banana".count("a"))
```

**Output**

```
3
```

---

## 3. Popular List Methods

### `append()`

```python
nums = [1, 2]
nums.append(3)
print(nums)
```

**Output**

```
[1, 2, 3]
```

### `extend()`

```python
nums = [1, 2]
nums.extend([3, 4])
print(nums)
```

**Output**

```
[1, 2, 3, 4]
```

### `insert()`

```python
nums = [1, 3]
nums.insert(1, 2)
print(nums)
```

**Output**

```
[1, 2, 3]
```

### `remove()`

```python
nums = [1, 2, 3]
nums.remove(2)
print(nums)
```

**Output**

```
[1, 3]
```

### `pop()`

```python
nums = [1, 2, 3]
print(nums.pop())
print(nums)
```

**Output**

```
3
[1, 2]
```

### `sort()`

```python
nums = [3, 1, 2]
nums.sort()
print(nums)
```

**Output**

```
[1, 2, 3]
```

### `reverse()`

```python
nums = [1, 2, 3]
nums.reverse()
print(nums)
```

**Output**

```
[3, 2, 1]
```

### `len()`

```python
print(len([1, 2, 3]))
```

**Output**

```
3
```

---

## 4. Popular Dictionary Methods

### `get()`

```python
d = {"a": 1}
print(d.get("a"))
print(d.get("b", 0))
```

**Output**

```
1
0
```

### `keys()`

```python
d = {"a": 1}
print(d.keys())
```

**Output**

```
dict_keys(['a'])
```

### `values()`

```python
d = {"a": 1}
print(d.values())
```

**Output**

```
dict_values([1])
```

### `items()`

```python
d = {"a": 1}
print(d.items())
```

**Output**

```
dict_items([('a', 1)])
```

### `update()`

```python
d = {"a": 1}
d.update({"b": 2})
print(d)
```

**Output**

```
{'a': 1, 'b': 2}
```

### `pop()`

```python
d = {"a": 1}
print(d.pop("a"))
print(d)
```

**Output**

```
1
{}
```

### `clear()`

```python
d = {"a": 1}
d.clear()
print(d)
```

**Output**

```
{}
```

---

## 5. Useful Built-in Functions

### `type()`

```python
print(type(10))
```

**Output**

```
<class 'int'>
```

### `range()`

```python
print(list(range(5)))
```

**Output**

```
[0, 1, 2, 3, 4]
```

### `sum()`

```python
print(sum([1, 2, 3]))
```

**Output**

```
6
```

### `max()` and `min()`

```python
print(max([1, 5, 2]))
print(min([1, 5, 2]))
```

**Output**

```
5
1
```

---

