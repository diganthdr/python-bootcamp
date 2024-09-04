# Datatypes and thier operations

Here is a list of common Python data types along with their operations and code snippets to illustrate their use:

### 1. **Integer (`int`)**

- **Description**: Represents whole numbers.
- **Operations**: Addition, subtraction, multiplication, division, modulus, exponentiation, floor division.

**Code Snippets**:
```python
a = 10
b = 3

# Addition
print(a + b)  # Output: 13

# Subtraction
print(a - b)  # Output: 7

# Multiplication
print(a * b)  # Output: 30

# Division
print(a / b)  # Output: 3.3333333333333335

# Modulus
print(a % b)  # Output: 1

# Exponentiation
print(a ** b)  # Output: 1000

# Floor Division
print(a // b)  # Output: 3
```

### 2. **Float (`float`)**

- **Description**: Represents real numbers (decimal values).
- **Operations**: Same as integers, but results can be floating-point numbers.

**Code Snippets**:
```python
x = 10.5
y = 4.2

# Addition
print(x + y)  # Output: 14.7

# Subtraction
print(x - y)  # Output: 6.3

# Multiplication
print(x * y)  # Output: 44.1

# Division
print(x / y)  # Output: 2.5

# Modulus
print(x % y)  # Output: 2.1

# Exponentiation
print(x ** y)  # Output: 86158.00878830031

# Floor Division
print(x // y)  # Output: 2.0
```

### 3. **String (`str`)**

- **Description**: Represents a sequence of characters.
- **Operations**: Concatenation, repetition, indexing, slicing, methods like `upper()`, `lower()`, `find()`, `replace()`.

**Code Snippets**:
```python
s1 = "Hello"
s2 = "World"

# Concatenation
print(s1 + " " + s2)  # Output: Hello World

# Repetition
print(s1 * 3)  # Output: HelloHelloHello

# Indexing
print(s1[1])  # Output: e

# Slicing
print(s1[1:4])  # Output: ell

# Uppercase
print(s1.upper())  # Output: HELLO

# Lowercase
print(s2.lower())  # Output: world

# Find substring
print(s1.find("l"))  # Output: 2

# Replace substring
print(s1.replace("l", "x"))  # Output: Hexxo
```

### 4. **List (`list`)**

- **Description**: Ordered, mutable collection of items.
- **Operations**: Indexing, slicing, appending, extending, inserting, removing, popping, sorting, reversing.

**Code Snippets**:
```python
numbers = [1, 2, 3, 4, 5]

# Indexing
print(numbers[2])  # Output: 3

# Slicing
print(numbers[1:3])  # Output: [2, 3]

# Appending
numbers.append(6)
print(numbers)  # Output: [1, 2, 3, 4, 5, 6]

# Extending
numbers.extend([7, 8])
print(numbers)  # Output: [1, 2, 3, 4, 5, 6, 7, 8]

# Inserting
numbers.insert(2, 10)
print(numbers)  # Output: [1, 2, 10, 3, 4, 5, 6, 7, 8]

# Removing
numbers.remove(10)
print(numbers)  # Output: [1, 2, 3, 4, 5, 6, 7, 8]

# Popping
popped_item = numbers.pop()
print(popped_item)  # Output: 8

# Sorting
numbers.sort()
print(numbers)  # Output: [1, 2, 3, 4, 5, 6, 7]

# Reversing
numbers.reverse()
print(numbers)  # Output: [7, 6, 5, 4, 3, 2, 1]
```

### 5. **Tuple (`tuple`)**

- **Description**: Ordered, immutable collection of items.
- **Operations**: Indexing, slicing, concatenation, repetition.

**Code Snippets**:
```python
t = (1, 2, 3, 4, 5)

# Indexing
print(t[1])  # Output: 2

# Slicing
print(t[1:3])  # Output: (2, 3)

# Concatenation
t2 = t + (6, 7)
print(t2)  # Output: (1, 2, 3, 4, 5, 6, 7)

# Repetition
print(t * 2)  # Output: (1, 2, 3, 4, 5, 1, 2, 3, 4, 5)
```

### 6. **Dictionary (`dict`)**

- **Description**: Unordered collection of key-value pairs.
- **Operations**: Adding, updating, deleting keys, accessing values, methods like `keys()`, `values()`, `items()`.

**Code Snippets**:
```python
d = {'a': 1, 'b': 2, 'c': 3}

# Accessing values
print(d['a'])  # Output: 1

# Adding a new key
d['d'] = 4
print(d)  # Output: {'a': 1, 'b': 2, 'c': 3, 'd': 4}

# Updating a value
d['a'] = 10
print(d)  # Output: {'a': 10, 'b': 2, 'c': 3, 'd': 4}

# Removing a key
del d['b']
print(d)  # Output: {'a': 10, 'c': 3, 'd': 4}

# Getting keys
print(d.keys())  # Output: dict_keys(['a', 'c', 'd'])

# Getting values
print(d.values())  # Output: dict_values([10, 3, 4])

# Getting items
print(d.items())  # Output: dict_items([('a', 10), ('c', 3), ('d', 4)])
```

### 7. **Set (`set`)**

- **Description**: Unordered collection of unique items.
- **Operations**: Adding, removing elements, union, intersection, difference, symmetric difference.

**Code Snippets**:
```python
s1 = {1, 2, 3, 4}
s2 = {3, 4, 5, 6}

# Adding an element
s1.add(5)
print(s1)  # Output: {1, 2, 3, 4, 5}

# Removing an element
s1.remove(5)
print(s1)  # Output: {1, 2, 3, 4}

# Union
print(s1 | s2)  # Output: {1, 2, 3, 4, 5, 6}

# Intersection
print(s1 & s2)  # Output: {3, 4}

# Difference
print(s1 - s2)  # Output: {1, 2}

# Symmetric Difference
print(s1 ^ s2)  # Output: {1, 2, 5, 6}
```

### 8. **Boolean (`bool`)**

- **Description**: Represents `True` or `False`.
- **Operations**: Logical operations (`and`, `or`, `not`).

**Code Snippets**:
```python
a = True
b = False

# Logical AND
print(a and b)  # Output: False

# Logical OR
print(a or b)  # Output: True

# Logical NOT
print(not a)  # Output: False
```

### 9. **None Type (`NoneType`)**

- **Description**: Represents the absence of a value or a null value.
- **Operations**: Typically used for default values in functions or to reset variables.

**Code Snippets**:
```python
x = None

# Check if x is None
if x is None:
    print("x is None")  # Output: x is None

# Assign a value
x = 10
print(x)  # Output: 10

# Reset to None
x = None
print(x)  # Output: None
```

These snippets provide a quick overview of the most common Python data types and some basic operations you can perform with each.
