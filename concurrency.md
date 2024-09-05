### Lesson on Concurrency in Python

**Concurrency** refers to the ability of a program to execute multiple tasks at once. Python provides several ways to implement concurrency, including threads, multiprocessing, and asynchronous programming. Understanding how to manage concurrency is essential for building scalable, efficient applications, especially when working with tasks like web scraping, I/O-bound operations, or handling multiple user requests.

---

### **Why Concurrency?**

Concurrency can dramatically improve the performance of programs that perform tasks like:
- **I/O-bound tasks:** Reading/writing files, network operations, or waiting for external data.
- **CPU-bound tasks:** Complex computations that can be split into parallel operations.

By handling multiple tasks concurrently, you can:
- Make efficient use of system resources.
- Improve the responsiveness of applications.
- Avoid blocking operations that would otherwise delay the entire program.

---

### **Concurrency Models in Python**

Python provides three primary ways to achieve concurrency:

1. **Multithreading**
2. **Multiprocessing**
3. **Asynchronous Programming (asyncio)**

Each of these approaches is suited to different types of problems.

---

### **1. Multithreading**

- **Definition:** Multithreading is the process of running multiple threads (lightweight processes) simultaneously within the same process. Each thread can perform a separate task, but all threads share the same memory space.
- **Use Case:** Multithreading is ideal for **I/O-bound** tasks where the program is often waiting for external resources (e.g., network responses, file I/O).
  
#### **Python Example: Multithreading**

```python
import threading
import time

def task(name):
    print(f"{name} started")
    time.sleep(2)  # Simulate a delay
    print(f"{name} completed")

# Creating threads
thread1 = threading.Thread(target=task, args=("Task 1",))
thread2 = threading.Thread(target=task, args=("Task 2",))

# Starting threads
thread1.start()
thread2.start()

# Wait for both threads to complete
thread1.join()
thread2.join()

print("All tasks completed")
```

**Explanation:**
- Two threads are created to run the `task` function simultaneously.
- The `start()` method begins thread execution, and `join()` ensures the main program waits for all threads to complete.

**Note:** Python’s **Global Interpreter Lock (GIL)** can limit the efficiency of multithreading in CPU-bound tasks because only one thread can execute Python bytecode at a time.

---

### **2. Multiprocessing**

- **Definition:** Multiprocessing involves running multiple processes, each with its own memory space and interpreter. It avoids the GIL limitations by using multiple processors/cores for true parallelism.
- **Use Case:** Multiprocessing is better suited for **CPU-bound** tasks where the program can benefit from true parallel execution.

#### **Python Example: Multiprocessing**

```python
import multiprocessing
import time

def task(name):
    print(f"{name} started")
    time.sleep(2)  # Simulate a delay
    print(f"{name} completed")

if __name__ == "__main__":
    # Creating processes
    process1 = multiprocessing.Process(target=task, args=("Process 1",))
    process2 = multiprocessing.Process(target=task, args=("Process 2",))

    # Starting processes
    process1.start()
    process2.start()

    # Wait for both processes to complete
    process1.join()
    process2.join()

    print("All processes completed")
```

**Explanation:**
- Here, each process runs in its own memory space, achieving true parallelism, especially on multi-core processors.

---

### **3. Asynchronous Programming (asyncio)**

- **Definition:** Asynchronous programming allows you to run functions concurrently without requiring multiple threads or processes. It uses an event loop to manage tasks, making it well-suited for tasks like network calls where the program can wait without blocking other operations.
- **Use Case:** `asyncio` is excellent for handling **I/O-bound** operations where tasks spend much time waiting for external resources (e.g., API calls, file reads/writes).

#### **Python Example: Asynchronous Programming with `asyncio`**

```python
import asyncio

async def task(name):
    print(f"{name} started")
    await asyncio.sleep(2)  # Simulate an I/O operation with a delay
    print(f"{name} completed")

async def main():
    # Run tasks concurrently
    await asyncio.gather(
        task("Task 1"),
        task("Task 2")
    )

# Running the event loop
asyncio.run(main())
```

**Explanation:**
- `async def` declares an asynchronous function, and `await` suspends its execution to allow other tasks to run.
- `asyncio.gather()` runs multiple asynchronous functions concurrently, and `asyncio.run()` starts the event loop.

---

### **Concurrency vs. Parallelism**

- **Concurrency** is about dealing with multiple tasks at once but not necessarily running them simultaneously. It’s useful for I/O-bound tasks where operations are delayed by external resources.
  
- **Parallelism** involves running tasks at the same time across multiple cores, making it beneficial for CPU-bound tasks. Multiprocessing in Python achieves true parallelism.

---

### **Choosing the Right Concurrency Model**

| Task Type      | Best Approach       | Example Use Case                               |
|----------------|---------------------|-----------------------------------------------|
| **I/O-bound**  | **Multithreading** or **Asyncio** | Web scraping, file I/O, network requests.      |
| **CPU-bound**  | **Multiprocessing**  | Data processing, complex calculations, encoding.|

---

### **Practice Exercises**

1. **Exercise 1: Multithreading**
   - Write a program that creates 5 threads, each printing a message after sleeping for a random amount of time (use `random` module for generating random sleep durations).

2. **Exercise 2: Multiprocessing**
   - Write a Python script that uses multiprocessing to calculate the sum of squares of numbers from 1 to 100. Split the calculation across 4 processes.

3. **Exercise 3: Asynchronous Programming**
   - Write an asynchronous program using `asyncio` that fetches data from two different APIs (use `httpbin.org/delay/2` for simulation). Both requests should be made concurrently, and the total time should be the time taken by the longest request.

4. **Exercise 4: Compare Concurrency Models**
   - Implement the same task (e.g., downloading a file from a URL) using multithreading, multiprocessing, and `asyncio`. Compare the performance and write a brief report explaining which method worked best and why.

---

### **Conclusion**

Concurrency in Python offers several options, each suitable for specific types of tasks. Understanding when to use multithreading, multiprocessing, or asynchronous programming can significantly improve the efficiency and performance of your applications.

