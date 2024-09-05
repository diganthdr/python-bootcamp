### **Databases in Python**

In Python, databases are commonly used to store, manage, and retrieve structured data. Python provides several libraries and modules to interact with databases, making it a versatile choice for database management. Python’s database connectivity includes support for both relational (SQL) and non-relational (NoSQL) databases.

---

### **Types of Databases in Python**

1. **Relational Databases (SQL)**
   - These databases use structured tables to store data and rely on SQL (Structured Query Language) for querying.
   - Examples: SQLite, MySQL, PostgreSQL, Microsoft SQL Server.

2. **Non-Relational Databases (NoSQL)**
   - These databases store data in a non-tabular format such as key-value pairs, documents, or graphs.
   - Examples: MongoDB, Cassandra, Redis.

---

### **Working with Relational Databases (SQL)**

The most common type of databases used with Python are **SQL databases**. Below are some popular Python libraries for working with SQL databases:

1. **SQLite**: Built-in database in Python.
2. **MySQL**: Popular open-source relational database management system.
3. **PostgreSQL**: Advanced open-source relational database system.

---

### **SQLite in Python**

SQLite is an embedded database that comes with Python and is easy to use for local or small-scale applications. 

#### **Setting Up SQLite**

The `sqlite3` module is part of Python’s standard library, so you don’t need to install anything.

```python
import sqlite3

# Create a connection to a database (or create a new one)
connection = sqlite3.connect('example.db')

# Create a cursor object to interact with the database
cursor = connection.cursor()

# Execute SQL commands using the cursor
cursor.execute('''CREATE TABLE IF NOT EXISTS users (id INTEGER PRIMARY KEY, name TEXT, age INTEGER)''')

# Commit the changes
connection.commit()

# Close the connection
connection.close()
```

---

#### **Inserting Data into SQLite Database**

You can insert data into the database using `INSERT INTO` SQL queries.

```python
# Reopen the connection and cursor
connection = sqlite3.connect('example.db')
cursor = connection.cursor()

# Insert data into the 'users' table
cursor.execute("INSERT INTO users (name, age) VALUES (?, ?)", ('Alice', 30))
cursor.execute("INSERT INTO users (name, age) VALUES (?, ?)", ('Bob', 24))

# Commit and close
connection.commit()
connection.close()
```

---

#### **Querying Data from SQLite Database**

To retrieve data from a database, use the `SELECT` statement.

```python
# Reopen the connection and cursor
connection = sqlite3.connect('example.db')
cursor = connection.cursor()

# Fetch all users from the 'users' table
cursor.execute("SELECT * FROM users")
rows = cursor.fetchall()

# Loop through the results
for row in rows:
    print(row)

# Close the connection
connection.close()
```

---

### **MySQL in Python**

To work with MySQL databases, you'll need to install the **mysql-connector-python** package.

```bash
pip install mysql-connector-python
```

#### **Connecting to MySQL**

```python
import mysql.connector

# Create a connection to the MySQL server
connection = mysql.connector.connect(
    host="localhost",
    user="yourusername",
    password="yourpassword",
    database="yourdatabase"
)

cursor = connection.cursor()

# Execute a simple SQL command
cursor.execute("CREATE TABLE IF NOT EXISTS users (id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(255), age INT)")

connection.close()
```

---

### **PostgreSQL in Python**

To work with PostgreSQL databases, you can use the **psycopg2** library.

```bash
pip install psycopg2
```

#### **Connecting to PostgreSQL**

```python
import psycopg2

# Create a connection to the PostgreSQL server
connection = psycopg2.connect(
    dbname="yourdatabase",
    user="yourusername",
    password="yourpassword",
    host="localhost"
)

cursor = connection.cursor()

# Execute SQL commands
cursor.execute("CREATE TABLE IF NOT EXISTS users (id SERIAL PRIMARY KEY, name VARCHAR(255), age INT)")

connection.commit()
connection.close()
```

---

### **Working with Non-Relational Databases (NoSQL)**

#### **MongoDB in Python**

MongoDB is a popular NoSQL database that stores data in JSON-like documents. To use MongoDB in Python, you can use the **pymongo** library.

#### **Installing pymongo**

```bash
pip install pymongo
```

#### **Connecting to MongoDB**

```python
from pymongo import MongoClient

# Create a connection to the MongoDB server
client = MongoClient('localhost', 27017)

# Create or select a database
db = client['mydatabase']

# Create or select a collection (table equivalent in SQL)
collection = db['users']

# Insert a document (equivalent to a row in SQL)
collection.insert_one({"name": "Alice", "age": 30})

# Query documents
for user in collection.find():
    print(user)
```

---

### **Best Practices When Working with Databases**

1. **Use parameterized queries** to prevent SQL injection attacks.
2. **Close the database connection** after performing operations to avoid leaving the connection open unnecessarily.
3. **Use transactions** for operations that require multiple steps to ensure data integrity.
4. **Normalize** your database schema to avoid redundancy and ensure efficient data storage.

---

### **Practice Exercises**

1. **Exercise 1**: 
   - Create an SQLite database named `company.db` with a table called `employees`. The table should have columns for `id`, `name`, `position`, and `salary`. Insert three rows into the table and query all the rows.

2. **Exercise 2**: 
   - Use MySQL to create a `students` table with columns for `id`, `name`, and `grade`. Insert five records and then retrieve the students with a grade higher than 80.

3. **Exercise 3**: 
   - Create a MongoDB collection called `products`. Insert three product documents with fields for `name`, `price`, and `category`. Query the collection to find all products in a specific category.

---

### **Conclusion**

Working with databases in Python is versatile and allows you to handle both relational (SQL) and non-relational (NoSQL) databases. Using libraries like `sqlite3`, `mysql-connector-python`, `psycopg2`, and `pymongo`, you can efficiently perform database operations such as creating tables, inserting data, querying data, and handling large datasets.
