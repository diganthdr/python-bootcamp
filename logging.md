### Python Logging Module: A Comprehensive Lesson

Logging is essential in software development for tracking events, debugging, and auditing. Python’s built-in `logging` module allows you to record various events in your code at different severity levels, store them in files, and provide meaningful diagnostics.

### Why Use Logging?
- Helps in debugging by capturing important runtime information.
- Monitors the application in production.
- Audits actions taken by users or processes.
- Can replace `print()` statements for better control and flexibility.

---

### Basics of Logging

The `logging` module provides functions to record messages, categorized by their severity.

#### Logging Levels:
Each level has a numeric value that determines its importance:
1. **DEBUG**: Detailed information, for diagnosing problems.
2. **INFO**: Confirmation that things are working as expected.
3. **WARNING**: An indication that something unexpected happened, but the software is still working.
4. **ERROR**: A more serious problem, the software has not been able to perform some function.
5. **CRITICAL**: A very serious error, the program may not be able to continue running.

### How to Log in Python

```python
import logging

# Basic configuration for logging
logging.basicConfig(level=logging.DEBUG)

# Logging messages
logging.debug("This is a debug message")
logging.info("This is an info message")
logging.warning("This is a warning message")
logging.error("This is an error message")
logging.critical("This is a critical message")
```

### Output:
```text
WARNING:root:This is a warning message
ERROR:root:This is an error message
CRITICAL:root:This is a critical message
```

- By default, logging messages of level **WARNING** and above are shown.
- You can adjust the logging level by setting `level=logging.DEBUG` to capture more detailed logs.

---

### Logging to a File

You can direct logging output to a file instead of the console.

```python
import logging

logging.basicConfig(filename='app.log', filemode='w', level=logging.DEBUG)

logging.debug("Debug message")
logging.info("Info message")
logging.warning("Warning message")
logging.error("Error message")
logging.critical("Critical message")
```

- **`filename='app.log'`**: Logs are written to a file named `app.log`.
- **`filemode='w'`**: Overwrites the log file each time the program runs. Use `'a'` for appending logs.

---

### Formatting Logs

To make logs more informative, you can format them with timestamps, log levels, and other details.

```python
import logging

logging.basicConfig(filename='app.log', 
                    level=logging.DEBUG,
                    format='%(asctime)s - %(levelname)s - %(message)s')

logging.info("Formatted log message")
```

**Common Formatting Options**:
- `%(asctime)s`: Time of the log entry.
- `%(levelname)s`: Log level (e.g., DEBUG, INFO).
- `%(message)s`: Log message.
- `%(filename)s`: File from which the log message is generated.

---

### Custom Loggers, Handlers, and Formatters

Python’s `logging` module allows more fine-grained control with custom loggers, handlers, and formatters.

#### Example:

```python
import logging

# Create a custom logger
logger = logging.getLogger('my_logger')

# Set the level for the logger
logger.setLevel(logging.DEBUG)

# Create handlers
console_handler = logging.StreamHandler()
file_handler = logging.FileHandler('file.log')

# Set level for handlers
console_handler.setLevel(logging.WARNING)
file_handler.setLevel(logging.DEBUG)

# Create formatter and add it to the handlers
formatter = logging.Formatter('%(asctime)s - %(name)s - %(levelname)s - %(message)s')
console_handler.setFormatter(formatter)
file_handler.setFormatter(formatter)

# Add handlers to the logger
logger.addHandler(console_handler)
logger.addHandler(file_handler)

# Test logging
logger.debug("This will go to the file but not to the console")
logger.warning("This will go to both the console and the file")
```

- **Custom Logger**: Created using `logging.getLogger()`. This is useful for creating multiple loggers in a large application.
- **Handlers**: Determine where the logs go (e.g., console, file). You can add multiple handlers to the same logger.
- **Formatter**: Adds structure and formatting to log messages.

### Using Multiple Loggers

You can create multiple loggers to separate logging concerns.

```python
import logging

# First logger for the application
app_logger = logging.getLogger('app')
app_logger.setLevel(logging.DEBUG)

# Second logger for database operations
db_logger = logging.getLogger('db')
db_logger.setLevel(logging.INFO)

app_logger.debug("App logger debug message")
db_logger.info("DB logger info message")
```

---

### Capturing Exceptions

You can use logging to capture and log exceptions.

```python
import logging

try:
    1 / 0
except ZeroDivisionError:
    logging.exception("An exception occurred")
```

This will log the exception traceback along with the message.

---

### Rotating Log Files

For long-running applications, you might want to limit the size of log files and archive old logs.

```python
import logging
from logging.handlers import RotatingFileHandler

# Setup rotating handler
handler = RotatingFileHandler('app.log', maxBytes=2000, backupCount=5)
logger = logging.getLogger('rotating_logger')
logger.setLevel(logging.INFO)
logger.addHandler(handler)

for i in range(1000):
    logger.info(f"Logging line {i}")
```

- **`maxBytes=2000`**: Log file will rotate once it reaches 2000 bytes.
- **`backupCount=5`**: Keeps up to 5 backup files (`app.log.1`, `app.log.2`, etc.).

---

### Best Practices

1. **Use proper log levels**: Ensure that you’re using appropriate levels (`DEBUG`, `INFO`, `WARNING`, etc.) to filter the importance of messages.
2. **Avoid using `print()` for debugging**: Use the logging module instead for flexibility and configurability.
3. **Log useful information**: Don't just log every action; log information that will help in diagnosing and understanding issues.
4. **Rotate logs in production**: Don’t let log files grow indefinitely; use log rotation techniques.
5. **Use separate loggers for different components**: If your application has multiple modules or subsystems, create separate loggers for each.

---

### Summary

The Python `logging` module is a powerful tool for tracking, debugging, and monitoring your applications. With support for multiple log levels, handlers, and formatters, it allows you to customize logging output and send logs to different destinations such as files or consoles. By following best practices, you can make logging an effective part of your development and production processes.

### Exercises

1. Write a Python program that logs different levels of messages to both the console and a file.
2. Modify the above program to format the logs with timestamps and the logger name.
3. Create a custom logger with two handlers: one for logging errors to a file and one for logging warnings and above to the console.
4. Implement rotating logs for a long-running Python application.
