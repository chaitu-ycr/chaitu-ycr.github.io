# 🧩 Functions in Python

Functions are reusable blocks of code that perform specific tasks. They promote modularity, readability, and maintainability by encapsulating logic into well-defined units.

## 📝 What is a Function?

A **function** is a named section of a program that performs a specific task. Functions help you:

- Avoid code repetition
- Organize code logically
- Make code easier to test and maintain

## 🛠️ Defining a Function

Use the `def` keyword to define a function:

```python
def function_name(parameters):
    """Docstring describing the function."""
    # Function body
    ...
```

| Syntax Element      | Description                                 |
|---------------------|---------------------------------------------|
| `def`               | Keyword to start a function definition      |
| `function_name`     | Name of the function                        |
| `parameters`        | Inputs to the function (optional)           |
| `"""Docstring"""`   | (Optional) Description of the function      |
| Function body       | The code block that runs when called        |

## 🧑‍💻 Calling a Function

Call a function by its name and provide any required arguments in parentheses:

```python
function_name(arguments)
```

## 🧩 Function Arguments

Functions can accept zero or more arguments (inputs) that provide data to the function.

| Argument Type      | Description                                      | Example                        |
|--------------------|--------------------------------------------------|--------------------------------|
| Positional         | Matched by position                              | `def add(x, y): ...`           |
| Keyword            | Matched by name                                  | `add(x=2, y=3)`                |
| Default            | Has a default value if not provided              | `def greet(name="World")`      |
| Variable-length    | Accepts any number of arguments                  | `*args`, `**kwargs`            |

**Examples:**

```python
def add(x, y):
    return x + y

print(add(2, 3))           # Positional: Output 5
print(add(x=4, y=5))       # Keyword: Output 9

def greet(name="World"):
    print(f"Hello, {name}!")

greet()                    # Default: Output Hello, World!
greet("Alice")             # Output Hello, Alice!
```

## 🧵 Variable-length Arguments

Use `*args` for variable positional arguments and `**kwargs` for variable keyword arguments.

```python
def print_args(*args, **kwargs):
    print("Positional:", args)
    print("Keyword:", kwargs)

print_args(1, 2, 3, a=4, b=5)
# Output:
# Positional: (1, 2, 3)
# Keyword: {'a': 4, 'b': 5}
```

## 🔄 Return Values

Functions can optionally return a value using the `return` statement. If no `return` is present, the function returns `None`.

```python
def multiply(a, b):
    """Returns the product of two numbers."""
    return a * b

product = multiply(4, 5)
print(product)  # Output: 20

def no_return():
    pass

print(no_return())  # Output: None
```

## 👋 Example: Greeting Function

```python
def greet(name):
    """This function greets a person by name."""
    print(f"Hello, {name}!")

greet("chaitu-ycr")
greet("Bob")
greet("Charlie")
```

## 🧰 More Examples

**Function with multiple return values:**

```python
def min_max(numbers):
    """Returns the minimum and maximum of a list."""
    return min(numbers), max(numbers)

low, high = min_max([3, 1, 4, 1, 5])
print(f"Min: {low}, Max: {high}")  # Output: Min: 1, Max: 5
```

**Function as argument:**

```python
def apply(func, value):
    return func(value)

print(apply(str.upper, "hello"))  # Output: HELLO
```

## 🏆 Best Practices

- Break down complex problems into smaller, well-defined functions.
- Use descriptive names that reflect the function's purpose.
- Write docstrings to explain what the function does and how to use it.
- Use default arguments for optional parameters.
- Keep functions focused on a single task.
- Avoid side effects unless necessary.

## 🗝️ Key Points

| Concept         | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| Reusability     | Write code once, use it many times                                          |
| Arguments       | Provide flexibility in how you use a function                               |
| Return Values   | Functions can provide data back to the calling code                         |
| Docstrings      | Enhance code readability and understanding                                  |
| Modularity      | Functions help organize code into logical, manageable sections              |

---