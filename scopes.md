# Scopes in python

In Python, the scope of a variable refers to the region of the code where the variable is recognized and can be accessed. Understanding variable scopes is crucial to managing and debugging code effectively. Python has four types of scopes, commonly referred to by the acronym **LEGB**: Local, Enclosing, Global, and Built-in.

### 1. **Local Scope**
- **Definition**: Variables defined inside a function have a local scope. They are only accessible within that function.
- **Example**:

```python
def my_function():
    x = 10  # x has a local scope
    print(x)  # Output: 10

my_function()
# print(x)  # This would raise an error because x is not accessible outside the function
```

### 2. **Enclosing (Nonlocal) Scope**
- **Definition**: Variables in the enclosing scope of nested functions (i.e., a function inside another function). These variables are accessible within the inner function.
- **Example**:

```python
def outer_function():
    x = 10  # x is in the enclosing scope

    def inner_function():
        nonlocal x
        x = 20  # Modify the enclosing scope variable
        print(x)  # Output: 20
    
    inner_function()
    print(x)  # Output: 20

outer_function()
```

- The `nonlocal` keyword allows you to modify a variable in the enclosing scope from within the inner function.

### 3. **Global Scope**
- **Definition**: Variables defined at the top level of a script or module have a global scope. They are accessible from any part of the code within that module or script.
- **Example**:

```python
x = 10  # x has a global scope

def my_function():
    print(x)  # Access the global variable x

my_function()  # Output: 10

# Modify global variable inside function
def update_global():
    global x
    x = 20  # Modify the global variable

update_global()
print(x)  # Output: 20
```

- The `global` keyword allows you to modify a global variable from within a function.

### 4. **Built-in Scope**
- **Definition**: This is the scope that contains the names of all the built-in functions and exceptions in Python. These names are always available in any scope.
- **Example**:

```python
# Built-in scope example
print(len([1, 2, 3]))  # Output: 3
```

- `len` is a built-in function that is available in all scopes.

### **Scope Resolution (LEGB Rule)**
- When you reference a variable in Python, the interpreter follows the **LEGB** rule to resolve the scope:
  1. **Local**: Looks in the local scope of the current function.
  2. **Enclosing**: If not found, it checks the enclosing scopes (for nested functions).
  3. **Global**: If still not found, it looks in the global scope.
  4. **Built-in**: Finally, it checks the built-in scope.

### **Example of Scope Resolution**:

```python
x = "global"

def outer():
    x = "enclosing"

    def inner():
        x = "local"
        print(x)  # Output: local
    
    inner()
    print(x)  # Output: enclosing

outer()
print(x)  # Output: global
```

### **Key Points**:
- Variables defined inside functions are local by default.
- Use `global` to modify a global variable inside a function.
- Use `nonlocal` to modify a variable in an enclosing scope.
- Python searches for variables using the LEGB rule.

Understanding scopes helps in writing cleaner, more bug-free code, especially when working with functions and modules.

# Is python different in terms of scopes from C/C++  language?
Yes, scopes in C are somewhat different from Python, though there are some similarities. Here's a comparison of the key differences and similarities:

### 1. **Local Scope**
   - **Python:** Variables declared inside a function are local to that function.
   - **C:** Similarly, variables declared inside a function or block (e.g., within `{}`) are local to that function or block.

   **Example in Python:**
   ```python
   def my_function():
       x = 10  # Local to this function
       print(x)

   my_function()
   ```

   **Example in C:**
   ```c
   void my_function() {
       int x = 10;  // Local to this function
       printf("%d", x);
   }
   ```

### 2. **Global Scope**
   - **Python:** Variables declared outside all functions are global and accessible from anywhere in the module.
   - **C:** Similarly, variables declared outside all functions are global, accessible from any function within the same file.

   **Example in Python:**
   ```python
   x = 10  # Global scope

   def my_function():
       print(x)  # Can access global variable

   my_function()
   ```

   **Example in C:**
   ```c
   int x = 10;  // Global scope

   void my_function() {
       printf("%d", x);  // Can access global variable
   }
   ```

### 3. **Block Scope**
   - **Python:** Variables declared inside `if`, `for`, `while`, or other blocks are still within the local or global scope; blocks do not create new scopes.
   - **C:** Blocks (such as those defined by `{}`) create a new scope. Variables declared within a block are local to that block.

   **Example in Python:**
   ```python
   if True:
       x = 5
   print(x)  # Accessible outside the if block
   ```

   **Example in C:**
   ```c
   void my_function() {
       if (1) {
           int x = 5;
           printf("%d", x);  // Accessible within the block
       }
       // printf("%d", x);  // Error: x is not accessible here
   }
   ```

### 4. **Static Variables**
   - **Python:** Python does not have a direct equivalent of C’s `static` variables, but you can achieve similar behavior using default function arguments or by using function attributes.
   - **C:** Variables declared as `static` inside a function retain their value between function calls and have a local scope to that function.

   **Example in C:**
   ```c
   void my_function() {
       static int x = 0;  // Retains value between calls
       x++;
       printf("%d", x);
   }

   int main() {
       my_function();  // Prints 1
       my_function();  // Prints 2
   }
   ```

### 5. **Enclosing (Nonlocal) Scope**
   - **Python:** Python supports enclosing (nonlocal) scope, where a nested function can access variables from its enclosing function.
   - **C:** C does not have a direct equivalent of Python's nonlocal scope; nested functions are not typically a feature in C.

   **Example in Python:**
   ```python
   def outer():
       x = 5

       def inner():
           nonlocal x
           x += 1
           print(x)

       inner()  # Prints 6
   ```

### Summary:
- **C** has a more granular scope control with block-level scopes and `static` variables.
- **Python** is more flexible with fewer scope levels, focusing on function-level scopes and using the LEGB rule (Local, Enclosing, Global, Built-in).

Understanding these differences is crucial when switching between or integrating C and Python code, especially in multi-language projects like those using Python with C extensions.
