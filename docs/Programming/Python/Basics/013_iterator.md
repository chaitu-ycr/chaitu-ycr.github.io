# 🌀 Python Iterators

## 🤔 What is an Iterator?
An **iterator** is an object that enables you to traverse a collection one element at a time, without loading the entire collection into memory. This is especially useful for large datasets or when you want to process elements sequentially.

## 🔄 Iterable vs. Iterator

| Term         | Description                                                                 | Examples                        |
|--------------|-----------------------------------------------------------------------------|---------------------------------|
| **Iterable** | An object capable of returning its members one at a time. Implements `__iter__()`. | Lists, Tuples, Strings, Dictionaries, Sets |
| **Iterator** | An object representing a stream of data; returns data one element at a time via `next()`. Implements both `__iter__()` and `__next__()`. | Objects returned by `iter()`    |

## 🧩 The Iterator Protocol

To be an iterator, an object must implement:
- `__iter__(self)`: Returns the iterator object itself.
- `__next__(self)`: Returns the next element. Raises `StopIteration` when no more elements.

## 🛠️ Using Iterators

### Obtaining an Iterator

You can obtain an iterator from any iterable using `iter()`:

```python
numbers = [1, 2, 3, 4, 5]
number_iterator = iter(numbers)
print(next(number_iterator))  # Output: 1
print(next(number_iterator))  # Output: 2
```

### Iterating with a `for` Loop

Python's `for` loop automatically uses the iterator protocol:

```python
for number in numbers:
    print(number)
```

**How it works internally:**
1. Calls `iter(numbers)` to get an iterator.
2. Repeatedly calls `next()` on the iterator.
3. Stops when `StopIteration` is raised.

## 🧑‍💻 Custom Iterators

You can create custom iterators by defining a class with `__iter__` and `__next__`:

```python
class CountDown:
    def __init__(self, start):
        self.current = start

    def __iter__(self):
        return self

    def __next__(self):
        if self.current <= 0:
            raise StopIteration
        value = self.current
        self.current -= 1
        return value

for num in CountDown(3):
    print(num)  # Output: 3, 2, 1
```

## 📄 Iterators in Practice

### File Iterator

Iterators are commonly used to process files line by line:

```python
with open('example.txt') as file:
    for line in file:
        print(line.strip())
```

### Generator Function Example

Generators are a simple way to create iterators:

```python
def fibonacci(limit):
    a, b = 0, 1
    while a < limit:
        yield a
        a, b = b, a + b

for num in fibonacci(10):
    print(num)  # Output: 0, 1, 1, 2, 3, 5, 8
```

## ⚡ Benefits of Using Iterators

| Benefit           | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| Memory Efficiency | Processes elements one at a time, reducing memory usage.                    |
| Lazy Evaluation   | Elements are generated only when needed (e.g., generators).                 |
| Flexibility       | Works with any data structure that supports iteration.                      |

## 📚 Common Use Cases

- Iterating over elements in lists, tuples, strings, dictionaries, and sets.
- Processing files line by line.
- Creating custom sequences using generator expressions or functions.
- Infinite sequences (e.g., `itertools.count`).

## 📝 Summary Table

| Feature         | Iterable         | Iterator                  |
|-----------------|------------------|---------------------------|
| Protocol        | `__iter__()`     | `__iter__()`, `__next__()`|
| Usage           | Can be looped over | Returns next item on demand |
| Example         | `[1, 2, 3]`      | `iter([1, 2, 3])`         |
| Memory Usage    | May load all data | Loads one item at a time  |