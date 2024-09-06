To showcase JSON parsing in Python, using various examples can help demonstrate different aspects of working with JSON. Here are a few sample JSON files with explanations and examples of how to parse them in Python:

### **1. Simple JSON Object**

**Example JSON**:
```json
{
    "name": "John Doe",
    "age": 30,
    "city": "New York"
}
```

**Python Parsing**:
```python
import json

json_data = '{"name": "John Doe", "age": 30, "city": "New York"}'
data = json.loads(json_data)

print(data['name'])  # Output: John Doe
print(data['age'])   # Output: 30
print(data['city'])  # Output: New York
```

### **2. JSON Array**

**Example JSON**:
```json
[
    {"name": "John", "age": 30},
    {"name": "Anna", "age": 22},
    {"name": "Peter", "age": 25}
]
```

**Python Parsing**:
```python
import json

json_data = '''
[
    {"name": "John", "age": 30},
    {"name": "Anna", "age": 22},
    {"name": "Peter", "age": 25}
]
'''
data = json.loads(json_data)

for person in data:
    print(person['name'], person['age'])
```

### **3. Nested JSON**

**Example JSON**:
```json
{
    "company": "Tech Inc.",
    "employees": [
        {
            "name": "Alice",
            "position": "Engineer",
            "skills": ["Python", "JavaScript"]
        },
        {
            "name": "Bob",
            "position": "Designer",
            "skills": ["Photoshop", "Illustrator"]
        }
    ]
}
```

**Python Parsing**:
```python
import json

json_data = '''
{
    "company": "Tech Inc.",
    "employees": [
        {
            "name": "Alice",
            "position": "Engineer",
            "skills": ["Python", "JavaScript"]
        },
        {
            "name": "Bob",
            "position": "Designer",
            "skills": ["Photoshop", "Illustrator"]
        }
    ]
}
'''
data = json.loads(json_data)

print(data['company'])
for employee in data['employees']:
    print(f"Name: {employee['name']}, Position: {employee['position']}")
    print(f"Skills: {', '.join(employee['skills'])}")
```

### **4. JSON with Mixed Data Types**

**Example JSON**:
```json
{
    "title": "Sample Data",
    "date": "2024-09-05",
    "items": [
        {"name": "Item1", "quantity": 5},
        {"name": "Item2", "quantity": 10}
    ],
    "active": true,
    "metadata": {
        "source": "example.com",
        "tags": ["sample", "json"]
    }
}
```

**Python Parsing**:
```python
import json

json_data = '''
{
    "title": "Sample Data",
    "date": "2024-09-05",
    "items": [
        {"name": "Item1", "quantity": 5},
        {"name": "Item2", "quantity": 10}
    ],
    "active": true,
    "metadata": {
        "source": "example.com",
        "tags": ["sample", "json"]
    }
}
'''
data = json.loads(json_data)

print(data['title'])
print(data['date'])
print("Active:", data['active'])
print("Source:", data['metadata']['source'])
print("Tags:", ', '.join(data['metadata']['tags']))

for item in data['items']:
    print(f"Item Name: {item['name']}, Quantity: {item['quantity']}")
```

### **5. Complex JSON with Deep Nesting**

**Example JSON**:
```json
{
    "organization": {
        "name": "Global Org",
        "departments": [
            {
                "department": "HR",
                "employees": [
                    {"name": "Jane", "age": 29},
                    {"name": "Steve", "age": 34}
                ]
            },
            {
                "department": "IT",
                "employees": [
                    {"name": "Bob", "age": 25},
                    {"name": "Alice", "age": 31}
                ]
            }
        ]
    }
}
```

**Python Parsing**:
```python
import json

json_data = '''
{
    "organization": {
        "name": "Global Org",
        "departments": [
            {
                "department": "HR",
                "employees": [
                    {"name": "Jane", "age": 29},
                    {"name": "Steve", "age": 34}
                ]
            },
            {
                "department": "IT",
                "employees": [
                    {"name": "Bob", "age": 25},
                    {"name": "Alice", "age": 31}
                ]
            }
        ]
    }
}
'''
data = json.loads(json_data)

print("Organization:", data['organization']['name'])
for department in data['organization']['departments']:
    print(f"Department: {department['department']}")
    for employee in department['employees']:
        print(f"  Employee Name: {employee['name']}, Age: {employee['age']}")
```

### **Summary**

These examples cover a range of JSON structures from simple objects to complex, deeply nested data. Parsing these in Python helps illustrate how to handle various JSON formats and navigate through nested data structures effectively.
