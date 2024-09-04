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

## Assignment
Here are some assignments focused on Python data types, including strings, lists, tuples, dictionaries, sets, and more:

### 1. **Basic Data Types**

**Assignment 1:**
- Create variables of different data types: `int`, `float`, `str`, and `bool`. Print each variable and its type.

**Assignment 2:**
- Write a function `data_types()` that takes a variable of any data type and returns a string describing the type of the variable.

### 2. **Strings**

**Assignment 3:**
- Write a function `string_operations(text)` that takes a string and performs the following operations:
  - Convert the string to uppercase.
  - Find the length of the string.
  - Replace spaces with underscores.
  - Return the modified string and its length.

**Assignment 4:**
- Create a function `reverse_words(sentence)` that takes a sentence and returns the sentence with each word reversed but the order of words unchanged.

### 3. **Lists**

**Assignment 5:**
- Create a function `list_operations(lst)` that takes a list of numbers and performs the following operations:
  - Append a number to the list.
  - Remove a number from the list.
  - Sort the list in ascending order.
  - Return the modified list.

**Assignment 6:**
- Write a function `merge_lists(list1, list2)` that merges two lists and removes any duplicate elements.

### 4. **Tuples**

**Assignment 7:**
- Define a function `tuple_operations(tpl)` that takes a tuple and performs the following operations:
  - Access an element by its index.
  - Count the number of occurrences of a specific element.
  - Return the tuple and its length.

**Assignment 8:**
- Create a function `swap_elements(tpl, index1, index2)` that takes a tuple and swaps the elements at the given indices. Return the modified tuple.

### 5. **Dictionaries**

**Assignment 9:**
- Write a function `dict_operations(d)` that takes a dictionary and performs the following operations:
  - Add a new key-value pair.
  - Remove a key-value pair.
  - Retrieve a value by its key.
  - Return the updated dictionary and the retrieved value.

**Assignment 10:**
- Create a function `merge_dicts(dict1, dict2)` that merges two dictionaries. If there are duplicate keys, values from the second dictionary should overwrite values from the first.

### 6. **Sets**

**Assignment 11:**
- Write a function `set_operations(s)` that takes a set and performs the following operations:
  - Add a new element to the set.
  - Remove an element from the set.
  - Perform a union with another set.
  - Return the modified set.

**Assignment 12:**
- Create a function `common_elements(set1, set2)` that returns a set containing elements that are common to both input sets.

### 7. **Type Conversion**

**Assignment 13:**
- Write a function `convert_types(data)` that takes a string representation of a number and converts it to `int` and `float`. Return both converted values.

**Assignment 14:**
- Create a function `to_string(data)` that takes any data type (e.g., `int`, `float`, `list`) and converts it to a string. Return the string representation.

### Answers

#### Assignment 1:
```python
int_var = 5
float_var = 3.14
str_var = "Hello"
bool_var = True

print(int_var, type(int_var))
print(float_var, type(float_var))
print(str_var, type(str_var))
print(bool_var, type(bool_var))
```

**Answer:**
```
5 <class 'int'>
3.14 <class 'float'>
Hello <class 'str'>
True <class 'bool'>
```

#### Assignment 2:
```python
def data_types(variable):
    return f"The type of the variable is: {type(variable).__name__}"

print(data_types(10))
print(data_types(3.14))
print(data_types("Hello"))
print(data_types([1, 2, 3]))
```

**Answer:**
```
The type of the variable is: int
The type of the variable is: float
The type of the variable is: str
The type of the variable is: list
```

#### Assignment 3:
```python
def string_operations(text):
    upper_text = text.upper()
    length = len(text)
    replaced_text = text.replace(" ", "_")
    return replaced_text, length

print(string_operations("Hello World"))
```

**Answer:**
```
('Hello_World', 11)
```

#### Assignment 4:
```python
def reverse_words(sentence):
    words = sentence.split()
    reversed_words = [word[::-1] for word in words]
    return ' '.join(reversed_words)

print(reverse_words("Hello World"))
```

**Answer:**
```
olleH dlroW
```

#### Assignment 5:
```python
def list_operations(lst):
    lst.append(10)
    lst.remove(5)
    lst.sort()
    return lst

print(list_operations([5, 2, 9, 1]))
```

**Answer:**
```
[1, 2, 9, 10]
```

#### Assignment 6:
```python
def merge_lists(list1, list2):
    merged_list = list1 + list2
    return list(set(merged_list))

print(merge_lists([1, 2, 3], [3, 4, 5]))
```

**Answer:**
```
[1, 2, 3, 4, 5]
```

#### Assignment 7:
```python
def tuple_operations(tpl):
    index = 1
    element = tpl[index]
    count = tpl.count(element)
    return tpl, count

print(tuple_operations((1, 2, 2, 3)))
```

**Answer:**
```
((1, 2, 2, 3), 2)
```

#### Assignment 8:
```python
def swap_elements(tpl, index1, index2):
    tpl = list(tpl)
    tpl[index1], tpl[index2] = tpl[index2], tpl[index1]
    return tuple(tpl)

print(swap_elements((1, 2, 3), 0, 2))
```

**Answer:**
```
(3, 2, 1)
```

#### Assignment 9:
```python
def dict_operations(d):
    d['new_key'] = 'new_value'
    del d['b']
    value = d.get('a')
    return d, value

print(dict_operations({'a': 1, 'b': 2}))
```

**Answer:**
```
({'a': 1, 'new_key': 'new_value'}, 1)
```

#### Assignment 10:
```python
def merge_dicts(dict1, dict2):
    merged_dict = dict1.copy()
    merged_dict.update(dict2)
    return merged_dict

print(merge_dicts({'a': 1}, {'b': 2, 'a': 3}))
```

**Answer:**
```
{'a': 3, 'b': 2}
```

#### Assignment 11:
```python
def set_operations(s):
    s.add(4)
    s.remove(1)
    s.union({5, 6})
    return s

print(set_operations({1, 2, 3}))
```

**Answer:**
```
{2, 3, 4, 5, 6}
```

#### Assignment 12:
```python
def common_elements(set1, set2):
    return set1.intersection(set2)

print(common_elements({1, 2, 3}, {2, 3, 4}))
```

**Answer:**
```
{2, 3}
```

#### Assignment 13:
```python
def convert_types(data):
    int_value = int(data)
    float_value = float(data)
    return int_value, float_value

print(convert_types("42.5"))
```

**Answer:**
```
(42, 42.5)
```

#### Assignment 14:
```python
def to_string(data):
    return str(data)

print(to_string(100))
print(to_string(3.14))
print(to_string([1, 2, 3]))
```

**Answer:**
```
100
3.14
[1, 2, 3]
```

These assignments should provide a comprehensive practice for handling various Python data types.
x = None
print(x)  # Output: None
```

These snippets provide a quick overview of the most common Python data types and some basic operations you can perform with each.
