File operations in Python are essential for working with files on your computer, such as reading from or writing to text files. 
Python provides built-in functions for handling files, making it easy to perform tasks like 
- creating
- reading
- writing
- appending and
- closing files.

### **1. Opening a File**

To open a file in Python, you use the `open()` function, which returns a file object. The `open()` function requires at least one argument: the name of the file you want to open. You can also specify the mode in which you want to open the file.

**Common Modes:**
- `"r"`: Read (default mode). Opens the file for reading.
- `"w"`: Write. Opens the file for writing (creates a new file or truncates an existing file).
- `"a"`: Append. Opens the file for appending (writing at the end of the file).
- `"x"`: Exclusive creation. Creates a new file, but fails if the file already exists.
- `"b"`: Binary mode. Opens the file in binary mode (e.g., `"rb"`, `"wb"`).
- `"t"`: Text mode (default). Opens the file in text mode (e.g., `"rt"`, `"wt"`).
- `"+"`: Read and write mode (e.g., `"r+"`, `"w+"`).

**Syntax:**
```python
file = open("filename.txt", "mode")
```

**Example:**
```python
file = open("example.txt", "r")  # Opens the file in read mode
```

### **2. Reading from a File**

There are several ways to read data from a file:

- **`read()`**: Reads the entire file or a specified number of characters.
- **`readline()`**: Reads one line at a time.
- **`readlines()`**: Reads all lines and returns them as a list.

**Example:**
```python
# Read the entire file
file = open("example.txt", "r")
content = file.read()
print(content)
file.close()
```

**Example (Reading line by line):**
```python
# Read line by line
file = open("example.txt", "r")
line = file.readline()
while line:
    print(line, end="")
    line = file.readline()
file.close()
```

### **3. Writing to a File**

To write to a file, you can use the `write()` or `writelines()` methods.

- **`write()`**: Writes a string to the file.
- **`writelines()`**: Writes a list of strings to the file.

**Example:**
```python
file = open("example.txt", "w")
file.write("Hello, World!\n")
file.write("This is a new line.")
file.close()
```

**Example (Writing multiple lines):**
```python
lines = ["First line\n", "Second line\n", "Third line\n"]
file = open("example.txt", "w")
file.writelines(lines)
file.close()
```

### **4. Appending to a File**

Appending data to a file means adding data to the end of the file without deleting the existing content.

**Example:**
```python
file = open("example.txt", "a")
file.write("This line is appended.\n")
file.close()
```

### **5. Closing a File**

After performing operations on a file, it’s good practice to close the file using the `close()` method. This frees up system resources.

**Example:**
```python
file = open("example.txt", "r")
content = file.read()
file.close()
```

### **6. Using `with` Statement**

The `with` statement in Python provides a clean and efficient way to handle files. It ensures that the file is properly closed after its suite finishes, even if an exception is raised.

**Example:**
```python
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
# No need to explicitly close the file
```

### **7. File Handling Methods**

Here are some common methods available for file objects:

- **`read(size)`**: Reads `size` bytes from the file. If `size` is omitted, it reads the entire file.
- **`readline()`**: Reads a single line from the file.
- **`readlines()`**: Reads all lines in a file and returns them as a list.
- **`write(string)`**: Writes the string to the file.
- **`writelines(list)`**: Writes a list of strings to the file.
- **`close()`**: Closes the file.
- **`seek(offset, whence)`**: Moves the file cursor to the specified position.
- **`tell()`**: Returns the current position of the file cursor.

### **8. Example: Reading and Writing a File**

Here’s a complete example that demonstrates reading from and writing to a file:

```python
# Writing to a file
with open("example.txt", "w") as file:
    file.write("This is the first line.\n")
    file.write("This is the second line.\n")

# Reading from the file
with open("example.txt", "r") as file:
    content = file.read()
    print(content)
```

**Output:**
```
This is the first line.
This is the second line.
```

### **9. Handling Exceptions**

When working with files, it’s essential to handle potential errors, such as trying to read a file that doesn’t exist. You can handle such exceptions using `try` and `except` blocks.

**Example:**
```python
try:
    file = open("non_existent_file.txt", "r")
except FileNotFoundError:
    print("The file does not exist.")
finally:
    file.close()
```

### **Practice Exercises**

1. **Reading and Writing:** Create a file named `data.txt` and write a few lines of text into it. Then, write a Python script to read and print the contents of the file.

2. **Word Count:** Write a Python program that reads a text file and counts the number of words in the file.

3. **Copying Files:** Write a Python script that copies the content of one file to another. Make sure that the destination file is not overwritten if it already exists.

4. **Find and Replace:** Write a Python program that reads a file, replaces all occurrences of a word with another word, and writes the result back to the file.

