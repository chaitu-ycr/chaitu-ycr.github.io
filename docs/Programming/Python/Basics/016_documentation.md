# 📝 Python Code Documentation

Documenting your code is essential for readability, maintainability, and collaboration. In Python, documentation is achieved through **comments** and **docstrings**. This guide covers both, including best practices, conventions, and practical examples.

---

## 🗨️ Comments

Comments are ignored by the Python interpreter and are meant for human readers. They help explain the code's functionality, logic, or non-obvious sections.

### Types of Comments

| Type             | Syntax Example                        | Description                                      |
|------------------|--------------------------------------|--------------------------------------------------|
| In-line Comment  | `x = 5  # set x to 5`                | Short comment on the same line as code           |
| Block Comment    | `# This is a block comment`<br>`# explaining multiple lines` | Multiple lines, each starting with `#`           |

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
> Triple-quoted strings (`""" ... """`) are only considered comments if not assigned or used as docstrings. Otherwise, they are ignored string literals.

### Best Practices for Comments

- ✅ Explain **why** something is done, not just **what**.
- ✅ Use comments for complex logic, non-obvious algorithms, or edge cases.
- ✅ Prefer clear variable and function names over excessive commenting.
- ❌ Avoid redundant comments that restate the code.

---

## 📄 Docstrings

Docstrings are special string literals placed at the beginning of a module, class, function, or method definition. They are accessible via the built-in `help()` function or the object's `__doc__` attribute.

### Docstring Structure

A typical docstring includes:

- **Short Summary:** Briefly describes the object/function/module.
- **Args:** List and describe arguments (for functions).
- **Returns:** Describe return value(s).
- **Raises:** List exceptions raised (if any).
- **Examples:** (Optional) Provide usage examples.

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

- Follow [PEP 257](https://peps.python.org/pep-0257/) for standard formatting.
- Use triple double quotes (`""" ... """`) for all docstrings.
- The first line should be a short summary.
- Leave a blank line after the summary, then add details.

---

## 🛠️ Comments vs. Docstrings

| Feature           | Comments                | Docstrings                |
|-------------------|------------------------|---------------------------|
| Purpose           | Explain code for humans | Document objects for users|
| Syntax            | `# ...`                 | `""" ... """`             |
| Location          | Anywhere in code        | Start of module/class/func|
| Access at runtime | No                      | Yes (`help()`, `__doc__`) |
| Used by tools     | No                      | Yes (Sphinx, IDEs, etc.)  |

---

---

## 🚀 Benefits of Good Documentation

- **Improved Readability:** Easier for others (and your future self) to understand.
- **Maintainability:** Simplifies debugging and updating code.
- **Collaboration:** Helps teams work together efficiently.
- **Automatic Documentation Generation:** Tools like Sphinx can generate docs from docstrings.
- **Code Reusability:** Clear docstrings help others use your code effectively.

---

> **Tip:**
> Use meaningful names for variables and functions to reduce the need for comments and to make your code self-documenting.