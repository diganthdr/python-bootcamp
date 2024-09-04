Python functions are a fundamental concept in programming that allow you to encapsulate code into reusable blocks. Here’s a rundown of the key aspects of functions in Python:

### 1. **Defining a Function**
Functions are defined using the `def` keyword, followed by the function name, parentheses (which may include parameters), and a colon. The function's code block is indented below the definition.

```python
def greet(name):
    print(f"Hello, {name}!")
```

### 2. **Calling a Function**
Once defined, you can call a function by using its name followed by parentheses. If the function takes arguments, you pass them inside the parentheses.

```python
greet("Alice")  # Output: Hello, Alice!
```

### 3. **Parameters and Arguments**
Functions can take parameters (inputs). These parameters are variables that you can use within the function. When you call the function, you pass arguments (values) to these parameters.

```python
def add(a, b):
    return a + b

result = add(5, 3)  # result is 8
```

### 4. **Return Statement**
The `return` statement is used to send a result from a function back to the caller. If no `return` statement is used, the function returns `None` by default.

```python
def square(x):
    return x * x

print(square(4))  # Output: 16
```

### 5. **Default Parameters**
You can provide default values for parameters. If an argument is not provided for a parameter with a default value, the default value is used.

```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()        # Output: Hello, Guest!
greet("Bob")   # Output: Hello, Bob!
```

### 6. **Keyword Arguments**
You can specify arguments by name when calling a function. This allows you to pass them in any order.

```python
def describe_person(name, age):
    print(f"{name} is {age} years old.")

describe_person(age=25, name="Alice")  # Output: Alice is 25 years old.
```

### 7. **Arbitrary Arguments**
Functions can accept an arbitrary number of positional and keyword arguments using `*args` and `**kwargs`.

- `*args` allows you to pass a variable number of positional arguments.
- `**kwargs` allows you to pass a variable number of keyword arguments.

```python
def list_numbers(*args):
    for number in args:
        print(number)

list_numbers(1, 2, 3, 4)

def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=25)
```

### 8. **Lambda Functions**
Lambda functions are small anonymous functions defined with the `lambda` keyword. They can have any number of arguments but only one expression.

```python
add = lambda x, y: x + y
print(add(2, 3))  # Output: 5
```

### 9. **Scope**
Variables defined inside a function are local to that function. They cannot be accessed from outside. However, you can use the `global` keyword to modify a global variable inside a function.

```python
x = 10

def modify_global():
    global x
    x = 20

modify_global()
print(x)  # Output: 20
```

### 10. **Docstrings**
Functions can have a docstring, which is a string literal that appears right after the function definition and is used to describe what the function does.

```python
def multiply(a, b):
    """Multiply two numbers."""
    return a * b

print(multiply.__doc__)  # Output: Multiply two numbers.
```

Understanding these concepts will help you effectively teach functions and demonstrate their importance in writing clean and reusable code.

## Assignment
Here are some assignments to help practice Python functions:

### 1. **Basic Function Practice**
- **Assignment 1:** Write a function `subtract(a, b)` that returns the result of subtracting `b` from `a`.
- **Assignment 2:** Create a function `is_even(number)` that returns `True` if the number is even and `False` otherwise.

### 2. **Function with Parameters**
- **Assignment 3:** Write a function `area_of_rectangle(length, width)` that calculates and returns the area of a rectangle.
- **Assignment 4:** Define a function `calculate_tax(amount, rate=0.05)` that calculates the tax on a given amount using a default rate of 5%. It should return the total amount including tax.

### 3. **Advanced Parameters and Return Values**
- **Assignment 5:** Create a function `power(base, exponent)` that returns the result of raising the base to the power of the exponent.
- **Assignment 6:** Write a function `max_of_three(a, b, c)` that returns the maximum of three numbers.

### 4. **Using *args and **kwargs**
- **Assignment 7:** Define a function `sum_all(*args)` that takes a variable number of arguments and returns their sum.
- **Assignment 8:** Write a function `print_person_info(**kwargs)` that takes a variable number of keyword arguments and prints each key-value pair.

### 5. **Lambda Functions**
- **Assignment 9:** Use a lambda function to create a function `multiply` that multiplies two numbers.
- **Assignment 10:** Create a lambda function that filters out all odd numbers from a list of integers.

### 6. **Practice with Scope**
- **Assignment 11:** Write a function `modify_list(lst)` that appends the value `10` to a given list. Verify that the list is modified outside the function.
- **Assignment 12:** Create a global variable `global_var`, write a function `update_global()` that changes the value of `global_var`, and demonstrate the change outside the function.

### 7. **Docstrings and Documentation**
- **Assignment 13:** Define a function `multiply_and_add(x, y, z)` that multiplies `x` and `y`, then adds `z` to the result. Write a meaningful docstring for this function.
- **Assignment 14:** Write a function `convert_to_uppercase(text)` that converts a given string to uppercase and include a docstring explaining its purpose.

### 8. **Practical Applications**
- **Assignment 15:** Write a function `fibonacci(n)` that returns the nth Fibonacci number. (Use a recursive approach if you want to challenge yourself.)
- **Assignment 16:** Define a function `count_vowels(text)` that counts the number of vowels in a given string.

These assignments should cover a range of concepts and help reinforce your understanding of Python functions.
