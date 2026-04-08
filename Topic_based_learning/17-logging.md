# Python Logging

## Introduction
Logging helps track events in an application, making debugging and monitoring easier. Python's `logging` module provides flexible logging capabilities.

## Basic Logging
```python
import logging

logging.basicConfig(level=logging.DEBUG)
logging.debug("This is a debug message")
logging.info("This is an info message")
logging.warning("This is a warning message")
logging.error("This is an error message")
logging.critical("This is a critical message")
```

### Log Levels
- `DEBUG`: Detailed information for troubleshooting.
- `INFO`: General information about program execution.
- `WARNING`: Indications of potential issues.
- `ERROR`: Errors that prevent function execution.
- `CRITICAL`: Severe errors causing program failure.

## Logging to a File
```python
logging.basicConfig(filename='app.log', level=logging.DEBUG, 
                    format='%(asctime)s - %(levelname)s - %(message)s')
logging.info("This message will be logged to a file")
```

## Custom Logger
```python
logger = logging.getLogger("my_logger")
logger.setLevel(logging.DEBUG)

file_handler = logging.FileHandler("custom.log")
formatter = logging.Formatter('%(asctime)s - %(levelname)s - %(message)s')
file_handler.setFormatter(formatter)

logger.addHandler(file_handler)
logger.debug("This is a debug message from custom logger")
```

## Summary
- Use `basicConfig()` for simple logging setup.
- Control logging levels (`DEBUG`, `INFO`, `WARNING`, `ERROR`, `CRITICAL`).
- Redirect logs to a file with `FileHandler`.
- Create custom loggers for modular logging.

