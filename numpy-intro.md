### **Introduction to NumPy**

**NumPy** (short for Numerical Python) is a powerful library in Python used for numerical and scientific computing. It provides support for working with arrays, matrices, and large datasets, enabling efficient mathematical operations on these data structures. NumPy is a foundational library for many other data science libraries, including **Pandas**, **SciPy**, and **TensorFlow**.

---

### **Key Features of NumPy**

1. **N-dimensional Array (ndarray)**: The core feature of NumPy is the **ndarray**, which allows you to work with multidimensional arrays. These arrays are similar to Python lists but come with many optimized functions for numerical operations.
   
2. **Mathematical Functions**: NumPy provides a wide range of mathematical functions for working with arrays, including vectorized operations that make computations faster.

3. **Broadcasting**: NumPy supports broadcasting, which allows arithmetic operations on arrays of different shapes.

4. **Linear Algebra Functions**: You can perform matrix operations, such as dot products, matrix inversions, and eigenvalue computations, with NumPy.

5. **Integration with Other Libraries**: NumPy integrates seamlessly with other libraries, such as Pandas, Matplotlib, and SciPy, making it a versatile tool for data science and scientific computing.

---

### **Installing NumPy**

To install NumPy, use `pip`:

```bash
pip install numpy
```

---

### **Working with NumPy Arrays**

#### **1. Creating Arrays**

You can create arrays from Python lists or tuples using the `np.array()` function.

```python
import numpy as np

# Create a 1D array
arr = np.array([1, 2, 3, 4, 5])
print(arr)

# Create a 2D array (matrix)
matrix = np.array([[1, 2, 3], [4, 5, 6]])
print(matrix)
```

#### **2. Array Attributes**

NumPy arrays have several attributes that provide information about their structure:

```python
# Shape of the array
print(arr.shape)  # (5,) -> 1D array with 5 elements

# Number of dimensions
print(matrix.ndim)  # 2 -> 2D array

# Data type of the elements
print(arr.dtype)  # int64 (on 64-bit systems)
```

#### **3. Array Initialization**

NumPy provides functions to create arrays initialized with specific values, such as zeros, ones, or random numbers.

```python
# Array of zeros
zeros = np.zeros((2, 3))
print(zeros)

# Array of ones
ones = np.ones((3, 3))
print(ones)

# Random array
random_array = np.random.rand(3, 2)
print(random_array)
```

---

### **Array Operations**

NumPy allows for element-wise arithmetic operations on arrays, which is much faster than using Python lists.

#### **1. Arithmetic Operations**

```python
# Create arrays
arr1 = np.array([1, 2, 3])
arr2 = np.array([4, 5, 6])

# Element-wise addition
print(arr1 + arr2)

# Element-wise multiplication
print(arr1 * arr2)

# Scalar multiplication
print(arr1 * 2)
```

#### **2. Mathematical Functions**

NumPy has many built-in mathematical functions, such as `np.sin()`, `np.log()`, and `np.mean()`.

```python
arr = np.array([1, 2, 3, 4, 5])

# Mean of the array
print(np.mean(arr))  # 3.0

# Sum of all elements
print(np.sum(arr))  # 15

# Square root of each element
print(np.sqrt(arr))
```

---

### **Array Slicing and Indexing**

You can access and modify specific elements, rows, or columns of a NumPy array using slicing.

```python
# Create a 2D array
matrix = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

# Access an element
print(matrix[1, 2])  # 6

# Access a row
print(matrix[1, :])  # [4 5 6]

# Access a column
print(matrix[:, 2])  # [3 6 9]

# Slicing a subarray
print(matrix[0:2, 1:3])  # [[2 3] [5 6]]
```

---

### **Broadcasting**

Broadcasting allows NumPy to perform operations on arrays of different shapes. It automatically expands the smaller array to match the shape of the larger array.

```python
arr1 = np.array([1, 2, 3])
arr2 = np.array([[10], [20], [30]])

# Broadcasting: arr1 is stretched to match arr2
result = arr1 + arr2
print(result)
# [[11 12 13]
#  [21 22 23]
#  [31 32 33]]
```

---

### **Linear Algebra with NumPy**

NumPy has many functions for linear algebra, such as matrix multiplication, transposition, and inversion.

#### **1. Matrix Multiplication**

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

# Matrix multiplication (dot product)
C = np.dot(A, B)
print(C)
```

#### **2. Matrix Transpose**

```python
# Transpose of a matrix
transpose_A = A.T
print(transpose_A)
```

#### **3. Inverse of a Matrix**

```python
# Inverse of a matrix
inv_A = np.linalg.inv(A)
print(inv_A)
```

---

### **Random Number Generation**

NumPy has a submodule, `numpy.random`, for generating random numbers and arrays.

```python
# Generate an array of random numbers between 0 and 1
rand_arr = np.random.rand(3, 3)
print(rand_arr)

# Generate an array of random integers
rand_ints = np.random.randint(0, 10, size=(3, 3))
print(rand_ints)
```

---

### **Practice Exercises**

1. **Exercise 1: Array Creation**
   - Create a 2D array of shape (4, 5) filled with random integers between 10 and 50.
   - Find the shape, size, and data type of the array.

2. **Exercise 2: Array Arithmetic**
   - Create two 1D arrays of size 5 with random integers.
   - Perform element-wise addition, subtraction, and multiplication.

3. **Exercise 3: Array Slicing**
   - Create a 3x3 matrix with values ranging from 1 to 9.
   - Extract the second row and the third column from the matrix.

4. **Exercise 4: Broadcasting**
   - Create a 1D array of size 4 and a 2D array of shape (4, 4).
   - Add the 1D array to each row of the 2D array using broadcasting.

5. **Exercise 5: Matrix Operations**
   - Create a 2x2 matrix and find its transpose.
   - Compute the inverse of the matrix and verify the result by multiplying the matrix by its inverse.

---
## Solutions
Here are the solutions for the **NumPy** exercises from the previous chapter:

---

### **Exercise 1: Array Creation**

- **Task**: Create a 2D array of shape (4, 5) filled with random integers between 10 and 50.
- **Find**: The shape, size, and data type of the array.

```python
import numpy as np

# Create a 2D array of shape (4, 5) filled with random integers between 10 and 50
array = np.random.randint(10, 50, size=(4, 5))

# Find the shape of the array
print("Shape of the array:", array.shape)

# Find the size of the array (number of elements)
print("Size of the array:", array.size)

# Find the data type of the array elements
print("Data type of the array elements:", array.dtype)

# Print the array
print("Array:\n", array)
```

---

### **Exercise 2: Array Arithmetic**

- **Task**: 
  - Create two 1D arrays of size 5 with random integers.
  - Perform element-wise addition, subtraction, and multiplication.

```python
# Create two 1D arrays of size 5 with random integers
arr1 = np.random.randint(1, 10, size=5)
arr2 = np.random.randint(1, 10, size=5)

# Element-wise addition
addition = arr1 + arr2

# Element-wise subtraction
subtraction = arr1 - arr2

# Element-wise multiplication
multiplication = arr1 * arr2

# Output the arrays and results
print("Array 1:", arr1)
print("Array 2:", arr2)
print("Addition:", addition)
print("Subtraction:", subtraction)
print("Multiplication:", multiplication)
```

---

### **Exercise 3: Array Slicing**

- **Task**: 
  - Create a 3x3 matrix with values ranging from 1 to 9.
  - Extract the second row and the third column from the matrix.

```python
# Create a 3x3 matrix with values from 1 to 9
matrix = np.arange(1, 10).reshape(3, 3)

# Extract the second row
second_row = matrix[1, :]

# Extract the third column
third_column = matrix[:, 2]

# Output the matrix and results
print("Matrix:\n", matrix)
print("Second row:", second_row)
print("Third column:", third_column)
```

---

### **Exercise 4: Broadcasting**

- **Task**:
  - Create a 1D array of size 4 and a 2D array of shape (4, 4).
  - Add the 1D array to each row of the 2D array using broadcasting.

```python
# Create a 1D array of size 4
arr1D = np.array([1, 2, 3, 4])

# Create a 2D array of shape (4, 4)
arr2D = np.random.randint(1, 10, size=(4, 4))

# Add the 1D array to each row of the 2D array using broadcasting
result = arr2D + arr1D

# Output the arrays and the result
print("1D array:", arr1D)
print("2D array:\n", arr2D)
print("Result after broadcasting:\n", result)
```

---

### **Exercise 5: Matrix Operations**

- **Task**:
  - Create a 2x2 matrix and find its transpose.
  - Compute the inverse of the matrix and verify the result by multiplying the matrix by its inverse.

```python
# Create a 2x2 matrix
matrix = np.array([[1, 2], [3, 4]])

# Transpose of the matrix
transpose = matrix.T

# Inverse of the matrix
inverse = np.linalg.inv(matrix)

# Multiply the matrix by its inverse to verify (should result in the identity matrix)
identity = np.dot(matrix, inverse)

# Output the results
print("Matrix:\n", matrix)
print("Transpose:\n", transpose)
print("Inverse:\n", inverse)
print("Matrix multiplied by its inverse (Identity matrix):\n", identity)
```

---

### **Explanation of Solutions:**

1. **Exercise 1** demonstrates how to create a random 2D array and retrieve its basic attributes like shape, size, and data type.
   
2. **Exercise 2** covers element-wise arithmetic operations on arrays, which are faster than using Python lists for the same task.

3. **Exercise 3** shows array slicing for extracting specific rows and columns, a fundamental operation for working with data in NumPy.

4. **Exercise 4** showcases broadcasting, allowing NumPy arrays of different shapes to be combined without explicit loops.

5. **Exercise 5** involves matrix operations such as transposing and finding the inverse, which are essential for linear algebra tasks.

These exercises provide a solid foundation for understanding how to manipulate arrays and matrices using NumPy, which is critical for scientific computing and data analysis.

### **Conclusion**

**NumPy** is a fundamental library for numerical computations in Python. It provides powerful array operations, efficient mathematical functions, and integrates seamlessly with other libraries used in data science and machine learning. Whether you’re dealing with large datasets, performing matrix operations, or working with random number generation, NumPy is an essential tool for fast and efficient computations.

