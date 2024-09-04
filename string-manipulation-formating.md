# String manipulation and formatting 
Python provides a rich set of operations for manipulating strings, as well as multiple ways to format them for display.

### **1. String Basics**

In Python, strings are sequences of characters enclosed in single quotes (`'`), double quotes (`"`), or triple quotes (`'''` or `"""` for multi-line strings).

**Example:**
```python
single_quote = 'Hello'
double_quote = "World"
multi_line = '''This is
a multi-line
string'''
```

### **2. String Indexing and Slicing**

- **Indexing:** Access individual characters in a string using square brackets. Python uses zero-based indexing.
- **Slicing:** Extract a substring by specifying a range of indices.

**Example:**
```python
text = "Python"
print(text[0])    # Output: P
print(text[-1])   # Output: n

# Slicing
print(text[0:3])  # Output: Pyt (from index 0 to 2)
print(text[3:])   # Output: hon (from index 3 to end)
print(text[:3])   # Output: Pyt (from start to index 2)
print(text[::2])  # Output: Pto (every second character)
```

### **3. String Methods**

Python provides many built-in methods for string manipulation. Here are some commonly used ones:

- **`len(string)`**: Returns the length of the string.
- **`string.lower()`**: Converts the string to lowercase.
- **`string.upper()`**: Converts the string to uppercase.
- **`string.strip()`**: Removes leading and trailing whitespace.
- **`string.replace(old, new)`**: Replaces occurrences of a substring.
- **`string.split(delimiter)`**: Splits the string into a list based on the delimiter.
- **`string.join(list)`**: Joins elements of a list into a string using a separator.
- **`string.find(substring)`**: Returns the index of the first occurrence of the substring.
- **`string.startswith(prefix)`**: Checks if the string starts with the specified prefix.
- **`string.endswith(suffix)`**: Checks if the string ends with the specified suffix.

**Example:**
```python
text = "  Hello, Python!  "
print(len(text))                 # Output: 17
print(text.lower())              # Output: "  hello, python!  "
print(text.strip())              # Output: "Hello, Python!"
print(text.replace("Python", "World"))  # Output: "  Hello, World!  "
print(text.split(","))           # Output: ['  Hello', ' Python!  ']
print("-".join(["a", "b", "c"])) # Output: "a-b-c"
print(text.find("Python"))       # Output: 8
print(text.startswith("  He"))   # Output: True
print(text.endswith("!  "))      # Output: True
```

### **4. String Concatenation**

You can concatenate (combine) strings using the `+` operator or by using the `join()` method.

**Example:**
```python
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name
print(full_name)  # Output: John Doe

# Using join()
names = ["John", "Doe"]
full_name = " ".join(names)
print(full_name)  # Output: John Doe
```

### **5. String Formatting**

String formatting allows you to create strings with embedded variables, making it easier to create dynamic text. There are several ways to format strings in Python:

#### **5.1 Old-style (`%`) Formatting**

This method uses the `%` operator for string formatting.

**Example:**
```python
name = "Alice"
age = 25
formatted_string = "My name is %s and I am %d years old." % (name, age)
print(formatted_string)  # Output: My name is Alice and I am 25 years old.
```

#### **5.2 `str.format()` Method**

The `str.format()` method allows more flexibility and readability.

**Example:**
```python
name = "Bob"
age = 30
formatted_string = "My name is {} and I am {} years old.".format(name, age)
print(formatted_string)  # Output: My name is Bob and I am 30 years old.

# You can also specify positions:
formatted_string = "My name is {0} and I am {1} years old.".format(name, age)
print(formatted_string)  # Output: My name is Bob and I am 30 years old.

# Named placeholders:
formatted_string = "My name is {name} and I am {age} years old.".format(name="Charlie", age=35)
print(formatted_string)  # Output: My name is Charlie and I am 35 years old.
```

#### **5.3 f-Strings (Formatted String Literals)**

Introduced in Python 3.6, f-strings are a concise and readable way to embed expressions inside string literals.

**Example:**
```python
name = "David"
age = 40
formatted_string = f"My name is {name} and I am {age} years old."
print(formatted_string)  # Output: My name is David and I am 40 years old.

# You can include expressions directly:
formatted_string = f"Next year, I will be {age + 1} years old."
print(formatted_string)  # Output: Next year, I will be 41 years old.
```

### **6. Advanced String Formatting**

You can control the appearance of formatted strings with additional options, such as specifying width, alignment, and precision.

**Example:**
```python
# Padding and alignment
number = 123.456
formatted_string = f"{number:10}"      # Default right-alignment
print(formatted_string)                # Output: "   123.456"

formatted_string = f"{number:<10}"     # Left-alignment
print(formatted_string)                # Output: "123.456   "

formatted_string = f"{number:^10}"     # Center-alignment
print(formatted_string)                # Output: " 123.456  "

# Formatting with precision
formatted_string = f"{number:.2f}"     # Output: "123.46"
print(formatted_string)

# Including commas as thousands separators
number = 1000000
formatted_string = f"{number:,}"       # Output: "1,000,000"
print(formatted_string)
```

### **7. Multi-line Strings and Escaping**

- **Multi-line Strings:** Use triple quotes (`'''` or `"""`) to create strings that span multiple lines.
- **Escaping:** Use the backslash (`\`) to include special characters in a string.

**Example:**
```python
multi_line_string = """This is a multi-line
string that spans
multiple lines."""

print(multi_line_string)

# Escaping special characters
escaped_string = "He said, \"Python is awesome!\""
print(escaped_string)  # Output: He said, "Python is awesome!"
```

### **8. String Immutability**

Strings in Python are immutable, meaning that once a string is created, it cannot be modified. Any operation that seems to modify a string will actually create a new string.

**Example:**
```python
text = "Hello"
text = text + " World"  # This creates a new string
print(text)             # Output: Hello World
```

### **9. Practice Exercises**

1. **String Slicing:** Given a string `"PythonProgramming"`, extract the substring `"Programming"` using slicing.

2. **String Manipulation:** Write a program that takes a sentence as input and returns the sentence with all vowels removed.

3. **String Formatting:** Format the string `"The price of {} is {} dollars."` using the `str.format()` method, where the first placeholder is `"apple"` and the second is `2`.

4. **String Alignment:** Write a program that takes a number as input and prints it right-aligned in a field of width 10.

5. **Count Characters:** Write a program that counts the number of occurrences of each character in a given string.


## Additional Exercises
### **String Manipulation Exercises**

1. **Palindrome Check:**
   - Write a function that checks if a given string is a palindrome (a string that reads the same forward and backward). Ignore case and spaces.
   - **Example Input:** `"A man a plan a canal Panama"`
   - **Expected Output:** `True`

2. **Character Frequency:**
   - Write a program that takes a string and returns a dictionary with the frequency of each character in the string.
   - **Example Input:** `"hello"`
   - **Expected Output:** `{'h': 1, 'e': 1, 'l': 2, 'o': 1}`

3. **Anagram Check:**
   - Write a function that checks if two strings are anagrams (strings that can be rearranged to form each other). Ignore case and spaces.
   - **Example Input:** `"Listen"`, `"Silent"`
   - **Expected Output:** `True`

4. **Reverse Words:**
   - Write a program that reverses the order of words in a given string.
   - **Example Input:** `"Python is fun"`
   - **Expected Output:** `"fun is Python"`

5. **Longest Word:**
   - Write a function that finds and returns the longest word in a sentence.
   - **Example Input:** `"The quick brown fox jumps over the lazy dog"`
   - **Expected Output:** `"jumps"`

6. **Count Vowels and Consonants:**
   - Write a program that counts the number of vowels and consonants in a given string.
   - **Example Input:** `"Hello World"`
   - **Expected Output:** `Vowels: 3, Consonants: 7`

7. **Remove Duplicates:**
   - Write a function that removes all duplicate characters from a string.
   - **Example Input:** `"programming"`
   - **Expected Output:** `"progamin"`

8. **Title Case Conversion:**
   - Write a program that converts a string into title case (the first letter of each word capitalized).
   - **Example Input:** `"this is a title"`
   - **Expected Output:** `"This Is A Title"`

9. **Swap Case:**
   - Write a function that swaps the case of all letters in a string (upper to lower and vice versa).
   - **Example Input:** `"Python Programming"`
   - **Expected Output:** `"pYTHON pROGRAMMING"`

10. **Remove Punctuation:**
    - Write a function that removes all punctuation from a string.
    - **Example Input:** `"Hello, world! How's it going?"`
    - **Expected Output:** `"Hello world Hows it going"`

### **String Formatting Exercises**

1. **Formatted Output of a List:**
   - Write a program that takes a list of items and prints them in a formatted string like: `"Item 1: apple, Item 2: banana, Item 3: cherry"`.
   - **Example Input:** `["apple", "banana", "cherry"]`
   - **Expected Output:** `"Item 1: apple, Item 2: banana, Item 3: cherry"`

2. **Custom Greeting Message:**
   - Write a function that takes a name and a message, then formats and prints the message as `"Hello [name], [message]"`.
   - **Example Input:** `("Alice", "welcome to Python programming!")`
   - **Expected Output:** `"Hello Alice, welcome to Python programming!"`

3. **Format Numbers with Leading Zeros:**
   - Write a program that takes a number as input and prints it with leading zeros to make it 6 digits long.
   - **Example Input:** `42`
   - **Expected Output:** `"000042"`

4. **Align Text in Columns:**
   - Write a program that prints three strings in three columns, with the strings right-aligned, left-aligned, and centered.
   - **Example Input:** `"Python"`, `"is"`, `"fun"`
   - **Expected Output:**
     ```
     Python   is       fun
        Python    is    fun
      Python  is  fun
     ```

5. **Price List:**
   - Write a program that formats and prints a list of items and their prices in a neat table format.
   - **Example Input:** `[("Apple", 0.5), ("Banana", 0.3), ("Cherry", 1.2)]`
   - **Expected Output:**
     ```
     Item       Price
     ----------------
     Apple      $0.50
     Banana     $0.30
     Cherry     $1.20
     ```

6. **Scientific Notation:**
   - Write a program that formats a given floating-point number in scientific notation.
   - **Example Input:** `123456.789`
   - **Expected Output:** `"1.234568e+05"`

7. **Percentage Formatting:**
   - Write a program that formats a given float as a percentage with two decimal places.
   - **Example Input:** `0.1234`
   - **Expected Output:** `"12.34%"`

8. **File Size Formatter:**
   - Write a function that formats a file size in bytes into a human-readable format (e.g., `1024` bytes as `1 KB`).
   - **Example Input:** `1048576`
   - **Expected Output:** `"1 MB"`

9. **Dynamic Padding:**
   - Write a program that takes a string and an integer, and prints the string padded with spaces to be the length of the integer.
   - **Example Input:** `("Hello", 10)`
   - **Expected Output:** `"Hello     "`

10. **Format Dates:**
    - Write a program that formats a given date as `"Day-Month-Year"` where Day, Month, and Year are two digits each.
    - **Example Input:** `1, 5, 2024`
    - **Expected Output:** `"01-05-2024"`
