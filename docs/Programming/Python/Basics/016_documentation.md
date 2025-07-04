# 📝 Python Code Documentation

Documenting your code is crucial for making it readable, maintainable, and easy to collaborate on. In Python, documentation is provided through **comments** and **docstrings**. This guide explains both, with best practices, conventions, and examples.

## 🗨️ Comments

Comments are ignored by Python and serve to clarify code for human readers. Use them to explain logic, intent, or complex sections.

### Types of Comments

| Type            | Syntax Example                         | Description                                 |
|-----------------|---------------------------------------|---------------------------------------------|
| In-line Comment | `x = 5  # set x to 5`                 | Short comment on the same line as code      |
| Block Comment   | `# This is a block comment`<br>`# explaining multiple lines` | Multiple lines, each starting with `#`      |

#### Examples

```python
# Store the user's name
user_name = "chaitu-ycr"  # In-line comment

# Block comment example:
# This function calculates the area of a rectangle.
# It takes width and height as arguments.
def calculate_area(width, height):
    return width * height

# Explain a complex algorithm step
for i in range(10):
    # Skip even numbers
    if i % 2 == 0:
        continue
    print(i)
```

> **Note:**
> Triple-quoted strings (`""" ... """`) are only comments if not assigned or used as docstrings; otherwise, they are ignored string literals.

### Comment Best Practices

- ✅ Explain **why** code exists, not just **what** it does.
- ✅ Use comments for complex logic or non-obvious code.
- ✅ Prefer descriptive names over excessive comments.
- ❌ Avoid comments that simply restate the code.

## 📄 Docstrings

Docstrings are special string literals at the start of modules, classes, functions, or methods. They are accessible via `help()` or the `__doc__` attribute.

### Docstring Structure

A typical docstring includes:

- **Short Summary:** Brief description.
- **Args:** Arguments (for functions).
- **Returns:** Return value(s).
- **Raises:** Exceptions raised (if any).
- **Examples:** (Optional) Usage examples.

#### Function Example

```python
def calculate_area(width: float, height: float) -> float:
    """
    Calculate the area of a rectangle.

    Args:
        width (float): The width of the rectangle.
        height (float): The height of the rectangle.

    Returns:
        float: The area of the rectangle.

    Raises:
        ValueError: If width or height is negative.

    Examples:
        >>> calculate_area(2, 3)
        6
        >>> calculate_area(0, 5)
        0
    """
    if width < 0 or height < 0:
        raise ValueError("Width and height must be non-negative.")
    return width * height
```

#### Class Example

```python
class Person:
    """
    Represents a person.

    Attributes:
        name (str): The person's name.
        age (int): The person's age.

    Example:
        >>> p = Person("Alice", 30)
        >>> p.greet()
        'Hello, my name is Alice.'
    """
    def __init__(self, name: str, age: int):
        self.name = name
        self.age = age

    def greet(self) -> str:
        """Return a greeting message."""
        return f"Hello, my name is {self.name}."
```

#### Module Example

```python
"""
math_utils.py

Utility functions for mathematical operations.

Functions:
    add(a, b): Return the sum of a and b.
    subtract(a, b): Return the difference of a and b.
"""
```

### Docstring Conventions

- Follow [PEP 257](https://peps.python.org/pep-0257/) for formatting.
- Use triple double quotes (`""" ... """`) for all docstrings.
- Start with a short summary.
- Leave a blank line after the summary before details.

## 🛠️ Comments vs. Docstrings

| Feature           | Comments                | Docstrings                |
|-------------------|------------------------|---------------------------|
| Purpose           | Explain code for humans | Document objects for users|
| Syntax            | `# ...`                 | `""" ... """`             |
| Location          | Anywhere in code        | Start of module/class/func|
| Access at runtime | No                      | Yes (`help()`, `__doc__`) |
| Used by tools     | No                      | Yes (Sphinx, IDEs, etc.)  |

## 🚀 Why Document?

- **Readability:** Easier for others (and yourself) to understand.
- **Maintainability:** Simplifies debugging and updates.
- **Collaboration:** Helps teams work together.
- **Automatic Documentation:** Tools like Sphinx generate docs from docstrings.
- **Reusability:** Clear docs help others use your code.

> **Tip:**
> Use meaningful names for variables and functions to make code self-documenting and reduce the need for comments.

## 🧪 Practice

1. Write docstrings for:
   - A function that calculates the factorial of a number.
   - A function that checks if a string is a palindrome.
   - A function that finds the maximum element in a list.
2. Create a `Car` class with attributes for make, model, and year. Add docstrings to the constructor and methods.
3. Implement a module for basic math operations (add, subtract, multiply, divide) with docstrings for each function.
4. Write a script using the `logging` module to log messages at different severity levels (DEBUG, INFO, WARNING, ERROR, CRITICAL).
5. Create a README for a Python project, including installation, usage, and contributing sections.
