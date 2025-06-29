# Python Q/A

## 1. Python Data Structures

### Tuple

**Q: What is a `tuple`? How is it different from a `list`?**  
A tuple is an immutable, ordered collection of items in Python. Unlike lists, tuples cannot be changed after creation (no add, remove, or update operations).  
Example:  
```python
my_tuple = (1, 2, 3)
my_list = [1, 2, 3]
# my_tuple[0] = 10  # Raises TypeError
my_list[0] = 10     # This works
```

**Q: Create a tuple with mixed data types.**  
```python
mixed_tuple = (1, "hello", 3.14, True)
print(mixed_tuple)  # Output: (1, 'hello', 3.14, True)
```

**Q: How do you check if an item exists in a tuple?**  
Use the `in` keyword.  
```python
t = (1, 2, 3)
print(2 in t)    # Output: True
print(5 in t)    # Output: False
```

**Q: Can you modify a tuple after creation? Why or why not?**  
No, tuples are immutable.  
```python
t = (1, 2, 3)
# t[0] = 10  # Raises TypeError
```

**Q: How do you concatenate two tuples?**  
Use the `+` operator.  
```python
t1 = (1, 2)
t2 = (3, 4)
t3 = t1 + t2
print(t3)  # Output: (1, 2, 3, 4)
```

**Q: Give an example of tuple unpacking.**  
```python
point = (10, 20)
x, y = point
print(x)  # Output: 10
print(y)  # Output: 20

# Extended unpacking
a, *b = (1, 2, 3, 4)
print(a)  # Output: 1
print(b)  # Output: [2, 3, 4]
```

---

### List

**Q: What is a `list`? How is it different from a `tuple`?**  
A list is a mutable, ordered collection of items in Python. Lists can be changed after creation (items can be added, removed, or updated).  
```python
my_list = [1, 2, 3]
my_list[0] = 10  # This works
# Lists use [], tuples use ()
```

**Q: Create a list with mixed data types.**  
```python
mixed_list = [1, "hello", 3.14, True]
print(mixed_list)  # Output: [1, 'hello', 3.14, True]
```

**Q: Demonstrate adding, removing, updating, and merging lists.**  
```python
lst = [1, 2, 3]
lst.append(4)         # Add
lst.remove(2)         # Remove
lst[0] = 10           # Update
lst2 = [5, 6]
merged = lst + lst2   # Merge
print(lst)            # Output: [10, 3, 4]
print(merged)         # Output: [10, 3, 4, 5, 6]
```

**Q: How do you search for an item in a list?**  
Use `in` or `index()`.  
```python
lst = [1, 2, 3]
print(2 in lst)         # Output: True
print(lst.index(3))     # Output: 2
```

**Q: Write a list comprehension to generate a list of squares from 1 to 10.**  
```python
squares = [x**2 for x in range(1, 11)]
print(squares)  # Output: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

**Q: How do you reverse a list?**  
Use `reverse()` or slicing.  
```python
lst = [1, 2, 3]
lst.reverse()
print(lst)         # Output: [3, 2, 1]

lst2 = [4, 5, 6]
print(lst2[::-1])  # Output: [6, 5, 4]
```

**Q: How do you sort a list of strings by length?**  
Use `sorted()` or `sort()` with `key=len`.  
```python
words = ['apple', 'fig', 'banana']
sorted_words = sorted(words, key=len)
print(sorted_words)  # Output: ['fig', 'apple', 'banana']
```

---

### Set

**Q: What is a `set`? How is it different from a `list` and a `tuple`?**  
A set is an unordered collection of unique, immutable elements. Sets do not allow duplicates and do not maintain order.  
```python
my_set = {1, 2, 3}
my_list = [1, 2, 2, 3]
my_tuple = (1, 2, 3)
print(my_set)   # Output: {1, 2, 3}
print(my_list)  # Output: [1, 2, 2, 3]
print(my_tuple) # Output: (1, 2, 3)
```

**Q: Create a set with unique elements.**  
```python
unique_set = {1, 2, 3, 4, 4, 5}
print(unique_set)  # Output: {1, 2, 3, 4, 5}
```

**Q: Demonstrate adding, removing, updating, and merging sets.**  
```python
s = {1, 2, 3}
s.add(4)            # Add
s.remove(2)         # Remove
s.update([5, 6])    # Update with multiple elements
s2 = {6, 7}
merged = s.union(s2)  # Merge (union)
print(s)             # Output: {1, 3, 4, 5, 6}
print(merged)        # Output: {1, 3, 4, 5, 6, 7}
```

**Q: How do you check if an item exists in a set?**  
Use `in`.  
```python
s = {1, 2, 3}
print(2 in s)    # Output: True
print(5 in s)    # Output: False
```

**Q: Write a set comprehension to generate all even numbers from 1 to 20.**  
```python
evens = {x for x in range(1, 21) if x % 2 == 0}
print(evens)  # Output: {2, 4, 6, 8, 10, 12, 14, 16, 18, 20}
```

**Q: How do you find the intersection and union of two sets?**  
Use `&` or `intersection()` for intersection, `|` or `union()` for union.  
```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a & b)                # Output: {3, 4}
print(a.intersection(b))    # Output: {3, 4}
print(a | b)                # Output: {1, 2, 3, 4, 5, 6}
print(a.union(b))           # Output: {1, 2, 3, 4, 5, 6}
```

---

### Dictionary

**Q: What is a `dictionary`? How is it different from other collections?**  
A dictionary is an unordered, mutable collection of key-value pairs. Keys must be unique and immutable; values can be any type.  
```python
my_dict = {'name': 'Alice', 'age': 25, 'city': 'New York'}
```

**Q: Create a dictionary with at least three key-value pairs.**  
```python
person = {
    'name': 'Bob',
    'age': 30,
    'country': 'USA'
}
print(person)  # Output: {'name': 'Bob', 'age': 30, 'country': 'USA'}
```

**Q: Demonstrate adding, removing, updating, and merging dictionaries.**  
```python
d = {'a': 1, 'b': 2}
d['c'] = 3              # Add
d['a'] = 10             # Update
del d['b']              # Remove
d2 = {'d': 4}
d.update(d2)            # Merge
print(d)                # Output: {'a': 10, 'c': 3, 'd': 4}
```

**Q: How do you check if a key exists in a dictionary?**  
Use `in`.  
```python
d = {'x': 1, 'y': 2}
print('x' in d)    # Output: True
print('z' in d)    # Output: False
```

**Q: Write a dictionary comprehension to map numbers 1-5 to their squares.**  
```python
squares = {x: x**2 for x in range(1, 6)}
print(squares)  # Output: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

**Q: How do you iterate over keys and values in a dictionary?**  
Use `.items()`.  
```python
d = {'a': 1, 'b': 2, 'c': 3}
for key, value in d.items():
    print(f"{key}: {value}")
# Output:
# a: 1
# b: 2
# c: 3
```

---

### String

**Q: What is a `string` in Python?**  
A string is an immutable sequence of Unicode characters, used to store and manipulate text data. Strings are defined using single, double, or triple quotes.

**Q: Create a string variable and demonstrate string concatenation.**  
```python
s1 = "Hello"
s2 = "World"
result = s1 + " " + s2
print(result)  # Output: Hello World
```

**Q: How do you join a list of strings into a single string?**  
Use `join()`.  
```python
words = ['Python', 'is', 'fun']
sentence = ' '.join(words)
print(sentence)  # Output: Python is fun
```

**Q: How do you search for a substring in a string?**  
Use `in`, `find()`, or `index()`.  
```python
text = "Hello, Python!"
print("Python" in text)        # Output: True
print(text.find("Python"))     # Output: 7
print(text.index("Python"))    # Output: 7
```

**Q: How do you split a string by a delimiter?**  
Use `split()`.  
```python
data = "apple,banana,cherry"
fruits = data.split(',')
print(fruits)  # Output: ['apple', 'banana', 'cherry']
```

**Q: How do you replace characters or words in a string?**  
Use `replace()`.  
```python
text = "I like apples"
new_text = text.replace("apples", "bananas")
print(new_text)  # Output: I like bananas
```

**Q: Explain string formatting with examples (`f-string`, `format()`, `%` operator).**  
- **f-string (Python 3.6+):**  
    ```python
    name = "Alice"
    age = 30
    print(f"My name is {name} and I am {age} years old.")
    # Output: My name is Alice and I am 30 years old.
    ```
- **`format()` method:**  
    ```python
    print("My name is {} and I am {} years old.".format(name, age))
    # Output: My name is Alice and I am 30 years old.
    ```
- **`%` operator:**  
    ```python
    print("My name is %s and I am %d years old." % (name, age))
    # Output: My name is Alice and I am 30 years old.
    ```

**Q: How do you reverse a string?**  
Use slicing with a step of `-1`.  
```python
s = "Python"
reversed_s = s[::-1]
print(reversed_s)  # Output: nohtyP
```

**Q: How do you check if a string is a palindrome?**  
Compare the string to its reverse.  
```python
def is_palindrome(s):
    return s == s[::-1]

print(is_palindrome("madam"))  # Output: True
print(is_palindrome("hello"))  # Output: False
```
## 2. Functions and Modules

### Functions

**Q: How do you define a function in Python?**  
Use the `def` keyword, followed by the function name and parentheses.  
Example:  
```python
def greet():
    print("Hello!")
```

---

**Q: Write a function that prints "Hello, World!".**  
```python
def say_hello():
    print("Hello, World!")

say_hello()  # Output: Hello, World!
```

---

**Q: Write a function that returns the square of a number.**  
```python
def square(x):
    return x * x

print(square(5))  # Output: 25
```

---

**Q: Write a function that accepts any number of arguments and prints them.**  
Use `*args` to accept a variable number of positional arguments.  
```python
def print_args(*args):
    for arg in args:
        print(arg)

print_args(1, "hello", 3.14)
# Output:
# 1
# hello
# 3.14
```

---

**Q: What is the difference between `*args` and `**kwargs`?**  
- `*args` collects extra positional arguments as a tuple.  
- `**kwargs` collects extra keyword arguments as a dictionary.  
Example:  
```python
def demo(*args, **kwargs):
    print("args:", args)
    print("kwargs:", kwargs)

demo(1, 2, three=3, four=4)
# Output:
# args: (1, 2)
# kwargs: {'three': 3, 'four': 4}
```

---

**Q: How do you document a function? Give an example with a docstring.**  
Use triple quotes inside the function to write a docstring.  
```python
def add(a, b):
    """
    Adds two numbers and returns the result.

    Parameters:
        a (int or float): First number.
        b (int or float): Second number.

    Returns:
        int or float: The sum of a and b.
    """
    return a + b

print(add.__doc__)
```

---

**Q: What is a lambda function? Give an example.**  
A lambda function is an anonymous, single-expression function defined with the `lambda` keyword.  
```python
square = lambda x: x * x
print(square(4))  # Output: 16
```

---

### Modules

**Q: What is a module in Python?**  
A module is a file containing Python code (functions, classes, variables) that can be imported and reused in other Python programs. Modules help organize code into separate files for better maintainability.

---

**Q: How do you create and import a module?**  
To create a module, save Python code in a `.py` file (e.g., `mymodule.py`).  
To import it, use the `import` statement.

Example (`mymodule.py`):
```python
def greet(name):
    print(f"Hello, {name}!")
```
Usage in another file:
```python
import mymodule
mymodule.greet("Alice")  # Output: Hello, Alice!
```

---

**Q: Write a module with a global variable and a function.**  
Example (`config.py`):
```python
PI = 3.14159

def area_of_circle(radius):
    return PI * radius * radius
```
Usage:
```python
import config
print(config.PI)  # Output: 3.14159
print(config.area_of_circle(2))  # Output: 12.56636
```

---

**Q: How do you import specific functions from a module?**  
Use the `from ... import ...` syntax.  
```python
from math import sqrt, pi
print(sqrt(16))  # Output: 4.0
print(pi)        # Output: 3.141592653589793
```

---

**Q: What is the use of `time.sleep()` in Python? Give an example.**  
`time.sleep(seconds)` pauses program execution for the specified number of seconds.  
```python
import time
print("Start")
time.sleep(2)  # Pauses for 2 seconds
print("End")
```

---

**Q: What is the difference between a module and a package?**  
- A **module** is a single Python file (`.py`) containing code.
- A **package** is a directory containing multiple modules and an `__init__.py` file (can be empty), allowing hierarchical organization of modules.

Example structure:
```
mypackage/
    __init__.py
    module1.py
    module2.py
```
Usage:
```python
from mypackage import module1
```

## 3. Object-Oriented Programming

### Classes and Objects

**Q: What is a class? What is an object?**  
A class is a blueprint for creating objects (instances) in Python. It defines attributes (data) and methods (functions) that describe the behavior of the objects.  
An object is an instance of a class, containing real values for the attributes defined by the class.

---

**Q: What is an attribute? What is a method?**  
- An **attribute** is a variable that belongs to a class or an object (e.g., `self.name`).
- A **method** is a function defined inside a class that operates on objects of that class (e.g., `def greet(self): ...`).

---

**Q: Write a class with attributes and methods. How do you create and use an object?**  
Example:
```python
class Person:
    def __init__(self, name, age):
        self.name = name      # attribute
        self.age = age        # attribute

    def greet(self):          # method
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")

p = Person("Alice", 30)  # create object
p.greet()                # Output: Hello, my name is Alice and I am 30 years old.
print(p.name)            # Output: Alice
print(p.age)             # Output: 30
```

---

**Q: What is the use of `self` in a class?**  
`self` refers to the current instance of the class. It is used to access attributes and methods of the class in Python.

Example:
```python
class Example:
    def set_value(self, value):
        self.value = value

    def get_value(self):
        return self.value

e = Example()
e.set_value(42)
print(e.get_value())  # Output: 42
```

---

**Q: What is inheritance? How do you inherit from a class? Give an example.**  
Inheritance allows a class (child/derived) to inherit attributes and methods from another class (parent/base).  
Example:
```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):  # Dog inherits from Animal
    def speak(self):
        print("Woof!")

a = Animal()
a.speak()  # Output: Animal speaks

d = Dog()
d.speak()  # Output: Woof!
```

---

**Q: What is method overriding?**  
Method overriding occurs when a subclass defines a method with the same name as a method in its parent class, replacing the parent’s implementation.

Example:
```python
class Parent:
    def show(self):
        print("Parent show")

class Child(Parent):
    def show(self):
        print("Child show")

c = Child()
c.show()  # Output: Child show
```

---

**Q: What is a class variable vs. an instance variable?**  
- A **class variable** is shared by all instances of the class.
- An **instance variable** is unique to each object.

Example:
```python
class Counter:
    count = 0  # class variable

    def __init__(self):
        Counter.count += 1
        self.id = Counter.count  # instance variable

a = Counter()
b = Counter()
print(a.id)        # Output: 1
print(b.id)        # Output: 2
print(Counter.count)  # Output: 2
```

---

**Q: What is a static method and a class method?**  
- A **static method** does not access class or instance data. Use `@staticmethod`.
- A **class method** receives the class as the first argument (`cls`). Use `@classmethod`.

Example:
```python
class Math:
    @staticmethod
    def add(x, y):
        return x + y

    @classmethod
    def description(cls):
        return f"This is {cls.__name__} class"

print(Math.add(2, 3))           # Output: 5
print(Math.description())       # Output: This is Math class
```

## 4. File Handling and Miscellaneous

### File Operations

**Q: How do you get the absolute path of the current script?**  
Use the `os` module and the `__file__` attribute:  
```python
import os
print(os.path.abspath(__file__))
```

---

**Q: How do you read, write, and append data to a text file?**  
Use the built-in `open()` function with appropriate modes:  
```python
# Write to a file
with open('example.txt', 'w') as f:
    f.write('Hello, World!\n')

# Read from a file
with open('example.txt', 'r') as f:
    content = f.read()
    print(content)  # Output: Hello, World!

# Append to a file
with open('example.txt', 'a') as f:
    f.write('Appended line.\n')
```

---

**Q: How do you read and write data to a JSON file?**  
Use the `json` module:  
```python
import json

data = {'name': 'Alice', 'age': 25}

# Write JSON to file
with open('data.json', 'w') as f:
    json.dump(data, f)

# Read JSON from file
with open('data.json', 'r') as f:
    loaded_data = json.load(f)
    print(loaded_data)  # Output: {'name': 'Alice', 'age': 25}
```

---

**Q: How do you handle exceptions when working with files?**  
Use `try-except` blocks to catch exceptions like `FileNotFoundError` or `IOError`:  
```python
try:
    with open('nonexistent.txt', 'r') as f:
        content = f.read()
except FileNotFoundError:
    print("File not found.")
except IOError as e:
    print(f"IO error occurred: {e}")
```

---

### Miscellaneous

**Q: How do you comment code in Python?**  
- Use `#` for single-line comments.
- Use triple quotes (`'''` or `"""`) for multi-line comments or docstrings.

Example:
```python
# This is a single-line comment

"""
This is a
multi-line comment or docstring.
"""
def foo():
    '''This is a function docstring.'''
    pass
```

---

**Q: What is threading? When should you use it?**  
- Threading allows concurrent execution of multiple parts of a program (threads).
- Use threading for I/O-bound tasks like file I/O, network operations, or waiting for user input in parallel.

---

**Q: How do you execute multiple functions in individual threads?**  
Use the `threading` module:  
```python
import threading

def func1():
    print("Function 1")

def func2():
    print("Function 2")

def func3():
    print("Function 3")

t1 = threading.Thread(target=func1)
t2 = threading.Thread(target=func2)
t3 = threading.Thread(target=func3)

t1.start()
t2.start()
t3.start()

t1.join()
t2.join()
t3.join()
```

## 5. Flow Control and Patterns

### Code Output and Patterns

**Q: What is the output of the following code?**
```python
animals = ['cat', 'dog']
for pet in animals:
    pet.upper()
print(animals)
```
**A:**  
The `upper()` method returns a new string but does not modify the original list elements.  
**Output:**  
```
['cat', 'dog']
```

---

**Q: What is the output of the following code?**
```python
for i in range(len(animals)):
    animals[i] = animals[i].upper()
print(animals)
```
**A:**  
This code updates each element in the list to its uppercase version.  
**Output:**  
```
['CAT', 'DOG']
```

---

**Q: What is the output of the following code?**
```python
numbers = [1, 2, 3, 4]
for i in numbers:
    numbers.append(i + 1)
print(numbers)
```
**A:**  
This creates an infinite loop because the list keeps growing as you append to it while iterating. In practice, this will eventually raise a `RuntimeError` or hang the program.  
**Example (partial output before interruption):**  
```
[1, 2, 3, 4, 2, 3, 4, 5, 3, 4, 5, 6, ...]
```
**Note:** Avoid modifying a list while iterating over it.

---

**Q: What is the output of the following code?**
```python
i = 6
while True:
    if i % 4 == 0:
        break
    print(i)
    i -= 2
```
**A:**  
- First iteration: `i = 6`, `6 % 4 = 2` (not 0), so print 6, then `i = 4`
- Second iteration: `i = 4`, `4 % 4 = 0`, so break

**Output:**  
```
6
```

---

**Q: Write code to print the following patterns:**

1.  
    ```
    *
    **
    ***
    ****
    ```
    ```python
    for i in range(1, 5):
        print('*' * i)
    ```
2.  
    ```
    1
    22
    333
    4444
    ```
    ```python
    for i in range(1, 5):
        print(str(i) * i)
    ```
3.  
    ```
    1
    12
    123
    1234
    ```
    ```python
    for i in range(1, 5):
        print(''.join(str(j) for j in range(1, i + 1)))
    ```

---

**Q: Write code to print each character in a word entered by the user.**
```python
word = input("Enter a word: ")
for char in word:
    print(char)
```

---

### Control Statements and Output

**Q: What is the output of the following code?**
```python
a = 0
for i in range(5):
    a = a + 1
    continue
print(a)
```
**A:**  
The loop runs 5 times, incrementing `a` each time.  
**Output:**  
```
5
```

---

**Q: What is the output of the following code?**
```python
for item in ('a', 'b', 'c', 'd'):
    print(item)
    if item == 'c':
        break
    continue
```
**A:**  
The loop prints each item. When `item` is `'c'`, it breaks out of the loop.  
**Output:**  
```
a
b
c
```

---

**Q: How do you check if an integer is even or odd using an `if` statement?**  
Use the modulo operator `%` to check divisibility by 2.  
Example:  
```python
num = 7
if num % 2 == 0:
    print("Even")
else:
    print("Odd")
# Output: Odd
```

---

**Q: What is the output of the following code?**
```python
i = j = 10
if i > j:
    print('i is greater than j')
elif i <= j:
    print('i is smaller than j')
else:
    print('both i and j are equal')
```
**A:**  
Since `i` and `j` are both 10, `i <= j` is `True`, so it prints:  
```
i is smaller than j
```
*Note: The logic is misleading; the message should be "i is smaller than or equal to j".*

---

**Q: How can the above code be written in one line?**  
Use a conditional expression (ternary operator):  
```python
print('i is greater than j' if i > j else 'i is smaller than j' if i <= j else 'both i and j are equal')
```

---

**Q: What is the output of the following code?**
```python
i = 2
j = 16
minimum_val = i < j and i or j
print(minimum_val)
```
**A:**  
`i < j` is `True`, so `minimum_val` is set to `i` (which is 2).  
**Output:**  
```
2
```
*Note: This is a common Python 2 idiom for a ternary operation, but for clarity, use `i if i < j else j` in modern code.*

---

**Q: What is conditional branching?**  
Conditional branching is the use of statements like `if`, `elif`, and `else` to execute different blocks of code based on conditions.  
Example:  
```python
x = 5
if x > 0:
    print("Positive")
else:
    print("Non-positive")
```

---

**Q: What is the output of the following code?**
```python
a = 0
b = 9
i = [True, False][a > b]
print(i)
```
**A:**  
`a > b` is `False` (which is 0), so `i = [True, False][0]` → `True`.  
**Output:**  
```
True
```

---

**Q: What is the difference between the `continue` and `pass` statements?**  
- `continue` skips the rest of the current loop iteration and moves to the next iteration.
- `pass` does nothing; it is a placeholder for future code.

Example:  
```python
for i in range(3):
    if i == 1:
        continue  # skips printing 1
    print(i)
# Output: 0 2

for i in range(3):
    if i == 1:
        pass  # does nothing
    print(i)
# Output: 0 1 2
```

---

**Q: What are the two major loop statements in Python?**  
- `for` loop: Iterates over a sequence (like list, tuple, string).
- `while` loop: Repeats as long as a condition is `True`.

---

**Q: What happens if you put an `else` statement after a `for` loop block?**  
The `else` block executes after the loop finishes normally (not by `break`).  
Example:  
```python
for i in range(3):
    print(i)
else:
    print("Done")
# Output:
# 0
# 1
# 2
# Done
```
If the loop is exited with `break`, the `else` block is skipped.

---

**Q: How do you use a ternary operator in Python?**  
The ternary operator is written as:  
```python
result = a if condition else b
```
Example:  
```python
x = 5
parity = "Even" if x % 2 == 0 else "Odd"
print(parity)  # Output: Odd
```

---

## 6. Exceptions and Error Handling

### Exceptions and Error Handling

**Q: What happens if a file is not found when opening it in Python?**  
If you try to open a file that does not exist in read mode, Python raises a `FileNotFoundError`. Handle it with a `try-except` block:
```python
try:
    f_n = input("Enter file name: ")
    i_f = open(f_n, 'r')
except FileNotFoundError:
    print("Input file not found")
```
It's best to catch specific exceptions rather than using a bare `except:`.

---

**Q: How many `except` statements can a `try-except` block have?**  
A `try` block can have multiple `except` clauses to handle different exception types:
```python
try:
    # some code
except ValueError:
    print("Value error")
except FileNotFoundError:
    print("File not found")
except Exception as e:
    print("Other exception:", e)
```
Only one matching `except` block will execute per exception.

---

**Q: What is the output of the following code?**
```python
def foo():
    try:
        return 1
    finally:
        return 2
k = foo()
print(k)
```
**A:**  
The `finally` block overrides the `return` in `try`.  
**Output:**  
```
2
```

---

**Q: What is the output of the following code?**
```python
def foo():
    try:
        print(1)
    finally:
        print(2)
foo()
```
**A:**  
The `try` block prints `1`, then `finally` prints `2`.  
**Output:**  
```
1
2
```

---

**Q: What happens when `'1' == 1` is executed?**  
Python compares a string (`'1'`) and an integer (`1`). They are different types, so the result is `False`:
```python
print('1' == 1)  # Output: False
```

---

**Q: What is the difference between `Exception` and `BaseException`?**  
- `BaseException` is the base class for all built-in exceptions.
- `Exception` is the base class for most user-defined and built-in exceptions, but not for system-exiting exceptions like `SystemExit`, `KeyboardInterrupt`, etc., which inherit directly from `BaseException`.
```python
issubclass(Exception, BaseException)  # True
issubclass(SystemExit, BaseException) # True
issubclass(SystemExit, Exception)     # False
```

---

**Q: How do you raise a custom exception?**  
Define a new exception class (inheriting from `Exception`) and use `raise`:
```python
class MyError(Exception):
    pass

raise MyError("Something went wrong")
```

---

**Q: How do you use `else` and `finally` with `try-except` blocks?**  
- The `else` block runs if no exception occurs in the `try` block.
- The `finally` block always runs, whether or not an exception occurred.
```python
try:
    print("Try block")
except Exception:
    print("Exception occurred")
else:
    print("No exception")
finally:
    print("Always runs")
```
**Output:**
```
Try block
No exception
Always runs
```

---

## 7. Advanced Topics (Optional)

### Generators

**Q: What is a generator? How do you create one?**  
A generator is a special type of iterator in Python that yields values one at a time using the `yield` keyword. Generators are memory-efficient for large data sets because they produce items on demand.

Example:
```python
def count_up_to(n):
    count = 1
    while count <= n:
        yield count
        count += 1

for num in count_up_to(3):
    print(num)
# Output:
# 1
# 2
# 3
```

---

### Decorators

**Q: What is a decorator? Give an example.**  
A decorator is a function that takes another function and extends or modifies its behavior without changing its code. Decorators are commonly used for logging, access control, and timing.

Example:
```python
def my_decorator(func):
    def wrapper():
        print("Before function call")
        func()
        print("After function call")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
# Output:
# Before function call
# Hello!
# After function call
```

---

### List Slicing

**Q: What is list slicing? Give examples.**  
List slicing extracts a portion of a list (or other sequence types) using the syntax `list[start:stop:step]`.

Examples:
```python
lst = [0, 1, 2, 3, 4, 5]
print(lst[1:4])    # Output: [1, 2, 3]
print(lst[:3])     # Output: [0, 1, 2]
print(lst[::2])    # Output: [0, 2, 4]
print(lst[::-1])   # Output: [5, 4, 3, 2, 1, 0]  # reversed list
```

---

### enumerate() and zip()

**Q: How do you use `enumerate()` and `zip()`?**  
- `enumerate()` adds a counter to an iterable and returns pairs of (index, value).
- `zip()` combines multiple iterables into tuples of corresponding elements.

Examples:
```python
# enumerate
fruits = ['apple', 'banana', 'cherry']
for idx, fruit in enumerate(fruits):
    print(idx, fruit)
# Output:
# 0 apple
# 1 banana
# 2 cherry

# zip
names = ['Alice', 'Bob']
scores = [85, 92]
for name, score in zip(names, scores):
    print(f"{name}: {score}")
# Output:
# Alice: 85
# Bob: 92
```

---

### Shallow vs. Deep Copy

**Q: What is the difference between `deepcopy` and `copy`?**  
- `copy.copy()` creates a shallow copy (copies the outer object, but nested objects are shared).
- `copy.deepcopy()` creates a deep copy (copies the object and all nested objects recursively).

Example:
```python
import copy

lst1 = [[1, 2], [3, 4]]
shallow = copy.copy(lst1)
deep = copy.deepcopy(lst1)

lst1[0][0] = 99
print(shallow)  # Output: [[99, 2], [3, 4]]  # inner list changed
print(deep)     # Output: [[1, 2], [3, 4]]   # deep copy unaffected
```

---

### Global Interpreter Lock (GIL)

**Q: What is the Global Interpreter Lock (GIL)?**  
The Global Interpreter Lock (GIL) is a mutex in CPython (the standard Python implementation) that allows only one thread to execute Python bytecode at a time. This limits multi-threaded programs from fully utilizing multiple CPU cores for CPU-bound tasks, but I/O-bound tasks can still benefit from threading.

---

### Virtual Environments

**Q: How do you use virtual environments in Python?**  
A virtual environment is an isolated Python environment for managing project-specific dependencies.

Basic usage:
```bash
# Create a virtual environment
python -m venv venv

# Activate (Windows)
venv\Scripts\activate

# Activate (macOS/Linux)
source venv/bin/activate

# Install packages
pip install requests

# Deactivate
deactivate
```
Virtual environments help avoid dependency conflicts between projects.

---
