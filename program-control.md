# `if`, `else`, and loops in Python. 

---

## **Lesson: Conditional Statements and Loops in Python**

### **1. Conditional Statements**

Conditional statements allow you to execute code based on certain conditions. The primary conditional statements in Python are `if`, `elif`, and `else`.

#### **1.1 The `if` Statement**

The `if` statement evaluates a condition and executes the code block inside it if the condition is `True`.

**Syntax:**
```python
if condition:
    # code to execute if condition is True
```

**Example:**
```python
age = 18
if age >= 18:
    print("You are an adult.")
```

**Output:**
```
You are an adult.
```

#### **1.2 The `else` Statement**

The `else` statement executes a block of code if the condition in the `if` statement is `False`.

**Syntax:**
```python
if condition:
    # code to execute if condition is True
else:
    # code to execute if condition is False
```

**Example:**
```python
age = 16
if age >= 18:
    print("You are an adult.")
else:
    print("You are not an adult.")
```

**Output:**
```
You are not an adult.
```

#### **1.3 The `elif` Statement**

The `elif` (short for "else if") statement allows you to check multiple conditions.

**Syntax:**
```python
if condition1:
    # code to execute if condition1 is True
elif condition2:
    # code to execute if condition2 is True
else:
    # code to execute if neither condition1 nor condition2 is True
```

**Example:**
```python
age = 20
if age < 13:
    print("You are a child.")
elif 13 <= age < 20:
    print("You are a teenager.")
else:
    print("You are an adult.")
```

**Output:**
```
You are an adult.
```

### **2. Loops**

Loops allow you to execute a block of code repeatedly. The two main types of loops in Python are `for` loops and `while` loops.

#### **2.1 The `for` Loop**

The `for` loop iterates over a sequence (like a list, tuple, or string) and executes the code block for each item in the sequence.

**Syntax:**
```python
for variable in sequence:
    # code to execute for each item in the sequence
```

**Example:**
```python
for i in range(5):
    print(i)
```

**Output:**
```
0
1
2
3
4
```

#### **2.2 The `while` Loop**

The `while` loop executes the code block as long as a specified condition is `True`.

**Syntax:**
```python
while condition:
    # code to execute as long as condition is True
```

**Example:**
```python
count = 0
while count < 5:
    print(count)
    count += 1
```

**Output:**
```
0
1
2
3
4
```

#### **2.3 Using `break` and `continue`**

- The `break` statement exits the loop prematurely.
- The `continue` statement skips the rest of the code inside the loop for the current iteration and proceeds with the next iteration.

**Example with `break`:**
```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

**Output:**
```
0
1
2
3
4
```

**Example with `continue`:**
```python
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)
```

**Output:**
```
1
3
5
7
9
```

### **3. Practice Exercises**

1. **Conditional Statements Exercise:**
   Write a program that checks if a number is positive, negative, or zero and prints a corresponding message.

2. **`for` Loop Exercise:**
   Write a program that prints all the even numbers between 1 and 20.

3. **`while` Loop Exercise:**
   Write a program that calculates the factorial of a number using a `while` loop.

4. **`break` and `continue` Exercise:**
   Write a program that prints numbers from 1 to 10, but skips the number 5 and stops the loop if the number is 8.
