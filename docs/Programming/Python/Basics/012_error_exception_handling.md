# 🛡️ Error and Exception Handling in Python

In Python, **errors** and **exceptions** are mechanisms to handle unexpected situations during program execution. They help prevent your program from crashing and allow you to recover gracefully or provide meaningful feedback.

## 🧩 Types of Errors

| Type            | Description                                                                 | Example                |
|-----------------|-----------------------------------------------------------------------------|------------------------|
| **Syntax Error**| Violation of Python grammar rules, detected before execution.               | `print("Hello"`        |
| **Exception**   | Runtime error occurring during execution (e.g., division by zero, file not found). | `10 / 0`               |

## ⚙️ Exception Handling Structure

Python uses the `try-except` block to handle exceptions.

```python
try:
    # Code that might raise an exception
    result = 10 / 0
    print(result)
except ZeroDivisionError:
    print("Oops! You cannot divide by zero.")
```

- `try`: Code that may raise an exception.
- `except`: Handles the specified exception.
- Multiple `except` blocks can be used for different exceptions.

## 🔄 `else` and `finally` Clauses

- **`else`**: Executes if no exception occurs in the `try` block.
- **`finally`**: Always executes, regardless of exceptions (useful for cleanup).

```python
try:
    result = 10 / 5
except ZeroDivisionError:
    print("Oops! You cannot divide by zero.")
else:
    print("The division operation was successful.")
finally:
    print("This always runs.")
```

## 🏷️ Common Exceptions

| Exception           | Description                                      | Example Code                        |
|---------------------|--------------------------------------------------|-------------------------------------|
| `ZeroDivisionError` | Division by zero                                 | `10 / 0`                            |
| `IndexError`        | Invalid list index                               | `mylist = [1,2]; mylist[10]`        |
| `NameError`         | Using an undefined variable                      | `print(x)` (if x not defined)       |
| `KeyError`          | Accessing a non-existent dictionary key          | `mydict = {}; mydict['missing']`    |
| `FileNotFoundError` | File operation on a non-existent file            | `open('nofile.txt')`                |
| `TypeError`         | Operation on incompatible types                  | `'2' + 2`                           |
| `ValueError`        | Operation on correct type but invalid value      | `int('abc')`                        |

**Handling Multiple Exceptions:**
```python
try:
    mylist = [1, 2, 3]
    print(mylist[5])
except IndexError:
    print("Index out of range!")
except Exception as e:
    print(f"An unexpected error occurred: {e}")
```

## 🚨 Raising Exceptions

You can intentionally raise exceptions using the `raise` statement.

```python
def validate_age(age):
    if age < 0:
        raise ValueError("Age cannot be negative.")
    print(f"Age is {age}")

try:
    validate_age(-5)
except ValueError as e:
    print(f"Validation error: {e}")
```

## 📝 Best Practices

- Use specific `except` blocks for different exception types.
- Avoid bare `except:` unless absolutely necessary.
- Use `finally` for cleanup (e.g., closing files or releasing resources).
- Document custom exceptions and when to raise them.
- Log exceptions for debugging in larger applications.

## 🗝️ Summary Table

| Feature         | Purpose                                              | Syntax Example                |
|-----------------|------------------------------------------------------|-------------------------------|
| `try`           | Wrap code that may raise exceptions                  | `try: ...`                    |
| `except`        | Handle specific exceptions                           | `except ValueError: ...`      |
| `else`          | Run if no exception occurs                           | `else: ...`                   |
| `finally`       | Always run (cleanup)                                 | `finally: ...`                |
| `raise`         | Manually trigger an exception                        | `raise Exception("msg")`      |

## 📚 Additional Resources

- [Python Official Docs: Errors and Exceptions](https://docs.python.org/3/tutorial/errors.html)
- [Real Python: Python Exceptions](https://realpython.com/python-exceptions/)

## 🧪 Practice Exercises

1. Write a function that takes a number and returns its reciprocal. Handle division by zero.
2. Create a program that reads a file and prints its contents. Handle the case where the file does not exist.
3. Implement a function that takes a list and returns the element at a given index. Handle `IndexError`.
4. Write a function that takes a string and converts it to an integer. Handle `ValueError` if the string is not a valid number.
5. Create a custom exception called `NegativeNumberError` that is raised when a negative number is encountered in a list.
