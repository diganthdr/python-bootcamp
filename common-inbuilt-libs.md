Python comes with a vast collection of in-built libraries that simplify various tasks, from basic file handling to complex data manipulation. Below are some of the most commonly used in-built libraries in Python, along with a brief overview and some practice exercises.

---

### **1. `os`**
The `os` module provides a way of interacting with the operating system. It allows you to work with file paths, directories, and environment variables, among other system-level tasks.

#### **Common Uses:**
- File and directory manipulation (creating, deleting, renaming files/folders).
- Fetching environment variables.
- Executing system commands.

Here are the Python scripts for each of the tasks:

### 1. Python script to list all files and directories in the current directory:
```python
import os

# List all files and directories in the current directory
for item in os.listdir('.'):
    print(item)
```

### 2. Python script that checks if a directory exists, and if not, creates it:
```python
import os

# Directory to check or create
directory = 'my_directory'

# Check if directory exists, if not, create it
if not os.path.exists(directory):
    os.makedirs(directory)
    print(f'Directory "{directory}" created.')
else:
    print(f'Directory "{directory}" already exists.')
```

### 3. Python script to change the current working directory to a specified directory and print its path:
```python
import os

# Specify the directory you want to change to
new_directory = '/path/to/directory'

try:
    os.chdir(new_directory)
    print(f'Current working directory changed to: {os.getcwd()}')
except FileNotFoundError:
    print(f'Directory "{new_directory}" does not exist.')
```

### 4. Python script that deletes all `.txt` files from a directory:
```python
import os

# Specify the directory where you want to delete .txt files
directory = '/path/to/directory'

# Iterate through all files in the specified directory
for filename in os.listdir(directory):
    if filename.endswith('.txt'):
        file_path = os.path.join(directory, filename)
        try:
            os.remove(file_path)
            print(f'Deleted: {file_path}')
        except Exception as e:
            print(f'Error deleting {file_path}: {e}')
```


---

### **2. `sys`**
The `sys` module provides access to system-specific parameters and functions. It allows you to manipulate the Python runtime environment, interact with command-line arguments, and control the interpreter.

#### **Common Uses:**
- Command-line argument handling.
- Exiting the program.
- Interacting with the Python runtime environment.

Here are the Python scripts for each task:

### 1. Python script that takes a filename as a command-line argument and prints its content:
```python
import sys

# Check if filename is provided as a command-line argument
if len(sys.argv) != 2:
    print("Usage: python script.py <filename>")
    sys.exit(1)

filename = sys.argv[1]

# Read and print the file content
try:
    with open(filename, 'r') as file:
        content = file.read()
        print(content)
except FileNotFoundError:
    print(f"File '{filename}' not found.")
```

### 2. Python program that prints the current Python version using the `sys` module:
```python
import sys

# Print the current Python version
print(f"Python version: {sys.version}")
```

### 3. Python program that accepts multiple command-line arguments and prints their sum:
```python
import sys

# Ensure arguments are provided
if len(sys.argv) < 2:
    print("Usage: python script.py <num1> <num2> ...")
    sys.exit(1)

# Convert arguments to integers and calculate the sum
try:
    numbers = [int(arg) for arg in sys.argv[1:]]
    print(f"Sum: {sum(numbers)}")
except ValueError:
    print("Please provide valid integers.")
```


---

### **3. `math`**
The `math` module provides mathematical functions such as trigonometry, logarithms, and factorials.

#### **Common Uses:**
- Trigonometric functions.
- Logarithmic and exponential functions.
- Factorial and square root.


### 1. Python function that calculates the factorial of a number using the `math` module:
```python
import math

def factorial(num):
    return math.factorial(num)

# Example usage
number = 5
print(f"The factorial of {number} is {factorial(number)}")
```

### 2. Program that calculates the sine, cosine, and tangent of a given angle:
```python
import math

def trig_functions(angle_degrees):
    angle_radians = math.radians(angle_degrees)
    
    sine = math.sin(angle_radians)
    cosine = math.cos(angle_radians)
    tangent = math.tan(angle_radians)
    
    return sine, cosine, tangent

# Example usage
angle = 45
sine, cosine, tangent = trig_functions(angle)
print(f"Sine of {angle}°: {sine}")
print(f"Cosine of {angle}°: {cosine}")
print(f"Tangent of {angle}°: {tangent}")
```

### 3. Function to find the greatest common divisor (GCD) of two numbers using `math.gcd()`:
```python
import math

def find_gcd(num1, num2):
    return math.gcd(num1, num2)

# Example usage
num1, num2 = 48, 18
print(f"The GCD of {num1} and {num2} is {find_gcd(num1, num2)}")
```

### 4. Python script that takes a number as input and prints its square root and logarithm:
```python
import math

def calculate_sqrt_log(number):
    sqrt = math.sqrt(number)
    log = math.log(number)  # Natural logarithm (base e)
    
    return sqrt, log

# Example usage
number = float(input("Enter a number: "))
sqrt, log = calculate_sqrt_log(number)
print(f"Square root of {number}: {sqrt}")
print(f"Natural logarithm of {number}: {log}")
```

---

### **4. `random`**
The `random` module provides functions to generate random numbers and selections, which are useful for simulations, games, and testing.

#### **Common Uses:**
- Generating random numbers.
- Shuffling sequences.
- Selecting random elements from a list.

#### **Practice Exercises:**
1. Write a Python script that generates a random number between 1 and 100.
2. Create a function that shuffles a list of numbers using `random.shuffle()`.
3. Write a script that simulates rolling a die 10 times and prints the results.
4. Implement a program that picks a random item from a list of strings.

---

### **5. `datetime`**
The `datetime` module allows you to manipulate dates and times, calculate time differences, and format dates and times.

#### **Common Uses:**
- Working with dates and times.
- Formatting date/time strings.
- Calculating time intervals.


### 1. Python program that prints the current date and time:
```python
from datetime import datetime

# Get the current date and time
current_datetime = datetime.now()

print(f"Current date and time: {current_datetime}")
```

### 2. Function that takes a date in string format and converts it to a `datetime` object:
```python
from datetime import datetime

def string_to_datetime(date_string):
    return datetime.strptime(date_string, "%Y-%m-%d")

# Example usage
date_string = "2024-09-05"
converted_date = string_to_datetime(date_string)
print(f"Converted date (datetime object): {converted_date}")
```

### 3. Program that calculates how many days are left until a given future date (e.g., New Year's):
```python
from datetime import datetime

def days_until(target_date):
    today = datetime.now()
    delta = target_date - today
    return delta.days

# Example usage: Days until next New Year's Day
new_year = datetime(year=2025, month=1, day=1)
days_left = days_until(new_year)
print(f"Days left until New Year's: {days_left}")
```

### 4. Program that formats the current date in different formats:
```python
from datetime import datetime

# Get the current date
current_date = datetime.now()

# Format in DD/MM/YYYY
format1 = current_date.strftime("%d/%m/%Y")

# Format in MM-DD-YYYY
format2 = current_date.strftime("%m-%d-%Y")

# Format in YYYY.MM.DD
format3 = current_date.strftime("%Y.%m.%d")

print(f"Current date in DD/MM/YYYY: {format1}")
print(f"Current date in MM-DD-YYYY: {format2}")
print(f"Current date in YYYY.MM.DD: {format3}")
```

These scripts demonstrate how to handle dates and times with Python's `datetime` module. You can modify them for specific use cases if needed.


---

### **6. `json`**
The `json` module allows you to work with JSON data, converting between Python dictionaries and JSON format.

#### **Common Uses:**
- Reading and writing JSON data.
- Parsing JSON strings.
- Converting Python objects to JSON and vice versa.


### 1. Python script that reads a JSON file and prints its contents:
```python
import json

def read_json(file_path):
    try:
        with open(file_path, 'r') as file:
            data = json.load(file)
            print(json.dumps(data, indent=4))  # Pretty print the JSON content
    except FileNotFoundError:
        print(f"File '{file_path}' not found.")
    except json.JSONDecodeError:
        print(f"Error decoding JSON from file '{file_path}'.")

# Example usage
file_path = 'data.json'
read_json(file_path)
```

### 2. Function that converts a Python dictionary into a JSON string:
```python
import json

def dict_to_json_string(data):
    return json.dumps(data, indent=4)

# Example usage
data = {
    "name": "John",
    "age": 30,
    "city": "New York"
}
json_string = dict_to_json_string(data)
print(json_string)
```

### 3. Program that reads a list of users from a JSON file and prints their names:
```python
import json

def print_user_names(file_path):
    try:
        with open(file_path, 'r') as file:
            users = json.load(file)
            for user in users:
                print(user.get('name', 'Unknown Name'))
    except FileNotFoundError:
        print(f"File '{file_path}' not found.")
    except json.JSONDecodeError:
        print(f"Error decoding JSON from file '{file_path}'.")

# Example usage (file should contain a list of users)
file_path = 'users.json'
print_user_names(file_path)
```

### 4. Python script that writes some sample data (e.g., a list of dictionaries) into a JSON file:
```python
import json

def write_sample_data(file_path):
    sample_data = [
        {"name": "Alice", "age": 25, "city": "Los Angeles"},
        {"name": "Bob", "age": 28, "city": "Chicago"},
        {"name": "Charlie", "age": 32, "city": "Boston"}
    ]
    
    try:
        with open(file_path, 'w') as file:
            json.dump(sample_data, file, indent=4)
        print(f"Sample data written to '{file_path}'.")
    except IOError:
        print(f"Error writing to file '{file_path}'.")

# Example usage
file_path = 'sample_data.json'
write_sample_data(file_path)
```


---

### **7. `re`**
The `re` module provides support for working with regular expressions in Python.

#### **Common Uses:**
- Finding patterns in text.
- Replacing patterns.
- Validating string formats (e.g., emails, phone numbers).

Here are the Python programs using the `re` module (regular expressions) for each of your requirements:

### 1. Python program that checks if a string contains only letters:
```python
import re

def is_only_letters(s):
    return bool(re.fullmatch(r'[A-Za-z]+', s))

# Example usage
string = "HelloWorld"
if is_only_letters(string):
    print(f"The string '{string}' contains only letters.")
else:
    print(f"The string '{string}' contains characters other than letters.")
```

### 2. Function that extracts all email addresses from a given text:
```python
import re

def extract_emails(text):
    # Regular expression pattern for extracting email addresses
    email_pattern = r'[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}'
    return re.findall(email_pattern, text)

# Example usage
text = "Contact us at support@example.com and info@website.org."
emails = extract_emails(text)
print(f"Extracted emails: {emails}")
```

### 3. Script that replaces all whitespace characters in a string with underscores using `re.sub()`:
```python
import re

def replace_whitespace_with_underscore(s):
    return re.sub(r'\s+', '_', s)

# Example usage
text = "This is    a sample text with  irregular spacing."
result = replace_whitespace_with_underscore(text)
print(f"Modified string: {result}")
```

### 4. Program that validates whether a string is a properly formatted phone number (e.g., `123-456-7890`):
```python
import re

def is_valid_phone_number(phone):
    # Regular expression pattern for validating phone numbers in the format 123-456-7890
    phone_pattern = r'^\d{3}-\d{3}-\d{4}$'
    return bool(re.fullmatch(phone_pattern, phone))

# Example usage
phone_number = "123-456-7890"
if is_valid_phone_number(phone_number):
    print(f"The phone number '{phone_number}' is valid.")
else:
    print(f"The phone number '{phone_number}' is invalid.")
```



---

### **8. `collections`**
The `collections` module provides specialized container datatypes like named tuples, ordered dictionaries, and default dictionaries.

#### **Common Uses:**
- Counting occurrences of elements using `Counter`.
- Working with ordered dictionaries using `OrderedDict`.
- Using `defaultdict` to handle missing keys in dictionaries.

Here are Python scripts utilizing the `collections` module for each task:

### 1. Python program that counts the frequency of each character in a string using `collections.Counter`:
```python
from collections import Counter

def count_characters(s):
    return Counter(s)

# Example usage
string = "hello world"
char_count = count_characters(string)
print(f"Character frequencies: {char_count}")
```

### 2. Program that creates a `defaultdict` where missing keys are automatically assigned a default value of `0`:
```python
from collections import defaultdict

def create_default_dict():
    # Create a defaultdict with default value of 0
    return defaultdict(int)

# Example usage
d = create_default_dict()
d['apple'] += 1
d['banana'] += 2
print(d)  # Output: defaultdict(<class 'int'>, {'apple': 1, 'banana': 2})
```

### 3. Python script that stores and prints student names and grades using `collections.namedtuple`:
```python
from collections import namedtuple

# Define a namedtuple for students
Student = namedtuple('Student', ['name', 'grade'])

def store_students():
    students = [
        Student(name="Alice", grade=90),
        Student(name="Bob", grade=85),
        Student(name="Charlie", grade=92)
    ]
    return students

# Example usage
students = store_students()
for student in students:
    print(f"Student: {student.name}, Grade: {student.grade}")
```

### 4. Function that sorts a dictionary based on its values using `OrderedDict`:
```python
from collections import OrderedDict

def sort_dict_by_value(d):
    # Sort the dictionary by its values
    sorted_dict = OrderedDict(sorted(d.items(), key=lambda x: x[1]))
    return sorted_dict

# Example usage
grades = {'Alice': 90, 'Bob': 85, 'Charlie': 92}
sorted_grades = sort_dict_by_value(grades)
print(f"Sorted dictionary: {sorted_grades}")
```


---

### **09. `subprocess`**
The `subprocess` module allows you to spawn new processes, connect to their input/output/error pipes, and retrieve their return codes.

#### **Common Uses:**
- Running shell commands.
- Working with external processes.
- Capturing command output.

### 1. Python script that runs the `ls` command (or `dir` on Windows) and prints the output:
```python
import subprocess

def list_directory():
    # Use 'dir' for Windows, 'ls' for Linux/Mac
    command = 'dir' if subprocess.os.name == 'nt' else 'ls'
    result = subprocess.run(command, shell=True, capture_output=True, text=True)
    print(result.stdout)

# Example usage
list_directory()
```

### 2. Function that runs a command-line program and returns its output:
```python
import subprocess

def run_command(command):
    result = subprocess.run(command, shell=True, capture_output=True, text=True)
    if result.returncode == 0:
        return result.stdout
    else:
        return result.stderr

# Example usage
command = 'echo Hello, World!'
output = run_command(command)
print(f"Command Output:\n{output}")
```

### 3. Program that runs a shell command to create a new directory using `subprocess`:
```python
import subprocess

def create_directory(directory_name):
    command = f'mkdir {directory_name}'
    result = subprocess.run(command, shell=True)
    if result.returncode == 0:
        print(f"Directory '{directory_name}' created successfully.")
    else:
        print(f"Failed to create directory '{directory_name}'.")

# Example usage
directory_name = 'new_folder'
create_directory(directory_name)
```

### 4. Python script that executes a ping command to check network connectivity:
```python
import subprocess

def ping_host(hostname):
    # 'ping' on Windows, 'ping -c 4' on Linux/Mac to send 4 packets
    command = f'ping -n 4 {hostname}' if subprocess.os.name == 'nt' else f'ping -c 4 {hostname}'
    result = subprocess.run(command, shell=True, capture_output=True, text=True)
    print(result.stdout)

# Example usage
hostname = 'google.com'
ping_host(hostname)
```

---

### **Conclusion:**
These are some of the most commonly used in-built libraries in Python, each designed to solve different problems and automate tasks. By practicing with these libraries, you'll gain a deeper understanding of how Python simplifies complex operations.

Let me know if you'd like specific answers or guidance on any of the exercises!
