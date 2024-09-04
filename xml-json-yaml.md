# Parsing XML, JSON, and YAML files in Python:

### **1. Parsing XML Files**

**Introduction to XML:**
- XML (eXtensible Markup Language) is a markup language used to store and transport data. It is both human-readable and machine-readable.

**Using `xml.etree.ElementTree`:**
- Python’s standard library provides the `xml.etree.ElementTree` module for parsing and creating XML data.

**Example:**
```python
import xml.etree.ElementTree as ET

# Sample XML data
xml_data = '''<note>
                <to>Tove</to>
                <from>Jani</from>
                <heading>Reminder</heading>
                <body>Don't forget me this weekend!</body>
              </note>'''

# Parse the XML data
root = ET.fromstring(xml_data)

# Access elements
to = root.find('to').text
from_ = root.find('from').text
heading = root.find('heading').text
body = root.find('body').text

print(f'To: {to}\nFrom: {from_}\nHeading: {heading}\nBody: {body}')
```

**Output:**
```
To: Tove
From: Jani
Heading: Reminder
Body: Don't forget me this weekend!
```

### **2. Parsing JSON Files**

**Introduction to JSON:**
- JSON (JavaScript Object Notation) is a lightweight data-interchange format that is easy for humans to read and write, and easy for machines to parse and generate.

**Using `json` module:**
- Python’s standard library provides the `json` module for parsing and manipulating JSON data.

**Example:**
```python
import json

# Sample JSON data
json_data = '''
{
    "name": "John",
    "age": 30,
    "city": "New York",
    "is_student": false,
    "courses": ["Math", "Science"]
}
'''

# Parse JSON data
data = json.loads(json_data)

# Access elements
name = data['name']
age = data['age']
city = data['city']
courses = data['courses']

print(f'Name: {name}\nAge: {age}\nCity: {city}\nCourses: {courses}')
```

**Output:**
```
Name: John
Age: 30
City: New York
Courses: ['Math', 'Science']
```

### **3. Parsing YAML Files**

**Introduction to YAML:**
- YAML (YAML Ain't Markup Language) is a human-readable data serialization format. It is often used for configuration files.

**Using `PyYAML`:**
- You need to install the `PyYAML` library to work with YAML files.

**Installation:**
```bash
pip install pyyaml
```

**Example:**
```python
import yaml

# Sample YAML data
yaml_data = '''
name: John
age: 30
city: New York
is_student: false
courses:
  - Math
  - Science
'''

# Parse YAML data
data = yaml.safe_load(yaml_data)

# Access elements
name = data['name']
age = data['age']
city = data['city']
courses = data['courses']

print(f'Name: {name}\nAge: {age}\nCity: {city}\nCourses: {courses}')
```

**Output:**
```
Name: John
Age: 30
City: New York
Courses: ['Math', 'Science']
```

### **Assignments for Practice**

1. **XML Parsing Exercise:**
   - Given an XML string with multiple books in a library, write a function to extract the title and author of each book.

2. **JSON Parsing Exercise:**
   - Given a JSON string representing a collection of employees, write a function to find the employee with the highest salary.

3. **YAML Parsing Exercise:**
   - Given a YAML string representing a list of servers and their configurations, write a function to find and print the details of the server with the most RAM.

### Solution 
(please attempt without referring this and then cross check when struck)

Here are the solutions for the assignments on parsing XML, JSON, and YAML files:

### **1. XML Parsing Exercise**

**Problem:**
Given an XML string with multiple books in a library, write a function to extract the title and author of each book.

**Solution:**
```python
import xml.etree.ElementTree as ET

# Sample XML data
xml_data = '''
<library>
    <book>
        <title>The Catcher in the Rye</title>
        <author>J.D. Salinger</author>
    </book>
    <book>
        <title>To Kill a Mockingbird</title>
        <author>Harper Lee</author>
    </book>
    <book>
        <title>1984</title>
        <author>George Orwell</author>
    </book>
</library>
'''

def extract_books(xml_data):
    root = ET.fromstring(xml_data)
    books = []
    for book in root.findall('book'):
        title = book.find('title').text
        author = book.find('author').text
        books.append({'title': title, 'author': author})
    return books

# Test the function
books = extract_books(xml_data)
for book in books:
    print(f"Title: {book['title']}, Author: {book['author']}")
```

**Output:**
```
Title: The Catcher in the Rye, Author: J.D. Salinger
Title: To Kill a Mockingbird, Author: Harper Lee
Title: 1984, Author: George Orwell
```

### **2. JSON Parsing Exercise**

**Problem:**
Given a JSON string representing a collection of employees, write a function to find the employee with the highest salary.

**Solution:**
```python
import json

# Sample JSON data
json_data = '''
[
    {"name": "Alice", "salary": 70000},
    {"name": "Bob", "salary": 80000},
    {"name": "Charlie", "salary": 120000}
]
'''

def find_highest_salary(json_data):
    employees = json.loads(json_data)
    highest_paid = max(employees, key=lambda x: x['salary'])
    return highest_paid

# Test the function
highest_paid = find_highest_salary(json_data)
print(f"Highest Paid Employee: {highest_paid['name']}, Salary: {highest_paid['salary']}")
```

**Output:**
```
Highest Paid Employee: Charlie, Salary: 120000
```

### **3. YAML Parsing Exercise**

**Problem:**
Given a YAML string representing a list of servers and their configurations, write a function to find and print the details of the server with the most RAM.

**Solution:**
```python
import yaml

# Sample YAML data
yaml_data = '''
servers:
  - name: server1
    ram: 16
    cpu: 4
    storage: 100
  - name: server2
    ram: 32
    cpu: 8
    storage: 200
  - name: server3
    ram: 64
    cpu: 16
    storage: 500
'''

def find_server_with_most_ram(yaml_data):
    data = yaml.safe_load(yaml_data)
    servers = data['servers']
    server_with_most_ram = max(servers, key=lambda x: x['ram'])
    return server_with_most_ram

# Test the function
server = find_server_with_most_ram(yaml_data)
print(f"Server with most RAM: {server['name']}, RAM: {server['ram']}GB, CPU: {server['cpu']} cores, Storage: {server['storage']}GB")
```

**Output:**
```
Server with most RAM: server3, RAM: 64GB, CPU: 16 cores, Storage: 500GB
```

