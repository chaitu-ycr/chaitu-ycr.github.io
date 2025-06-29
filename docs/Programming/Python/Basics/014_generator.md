# ⚡ Generators in Python

Generators are a powerful and memory-efficient way to create iterators in Python. They yield values one at a time, making them ideal for large datasets or infinite sequences.

---

## 🤔 What Are Generators?

- Special functions that return an **iterator object**.
- Use the `yield` statement to produce a series of values, pausing and resuming their state as needed.
- Defined using `def` and `yield`.

---

## 🛠️ Creating a Generator

A generator function uses `yield` to return values one at a time:

```python
def count_up_to(n):
    count = 1
    while count <= n:
        yield count
        count += 1

counter = count_up_to(3)
print(next(counter))  # 1
print(next(counter))  # 2
print(next(counter))  # 3
```

You can also iterate using a `for` loop:

```python
for num in count_up_to(3):
    print(num)  # 1, 2, 3
```

---

## 🆚 Regular Functions vs Generator Functions

| Feature                | Regular Function           | Generator Function           |
|------------------------|---------------------------|-----------------------------|
| Returns                | Single value (`return`)   | Iterator object (`yield`)    |
| Execution              | Runs all at once          | Pauses and resumes          |
| State retention        | No                        | Yes, between yields         |
| Memory usage           | Stores all values         | Generates values on demand  |

---

## 💡 Benefits of Generators

- **Memory Efficiency:** Do not store all values in memory at once.
- **Lazy Evaluation:** Values are generated only when requested.
- **Conciseness:** Generator expressions offer a compact way to create iterators.
- **Infinite Sequences:** Can represent infinite or very large sequences without memory issues.

---

## 🔥 Common Use Cases

- Generating large or infinite sequences (e.g., Fibonacci, primes)
- Processing files line by line
- Creating custom iterators for complex data structures
- Streaming data processing

---

## 🧮 Examples

### Fibonacci Sequence

```python
def fibonacci_generator(n):
    """Generates n Fibonacci numbers."""
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

for number in fibonacci_generator(7):
    print(number)  # 0, 1, 1, 2, 3, 5, 8
```

### Reading Large Files Line by Line

```python
def read_large_file(filepath):
    with open(filepath) as f:
        for line in f:
            yield line.strip()

# Usage:
# for line in read_large_file("big.txt"):
#     process(line)
```

### Infinite Sequence

```python
def infinite_counter(start=0):
    while True:
        yield start
        start += 1

counter = infinite_counter()
for _ in range(5):
    print(next(counter))  # 0, 1, 2, 3, 4
```

---

## 📝 Generator Expressions

Similar to list comprehensions, but use parentheses `()`:

```python
squares = (x*x for x in range(5))
for sq in squares:
    print(sq)  # 0, 1, 4, 9, 16
```

---

## 🗝️ Key Points

- Use `yield` to produce a sequence of values on demand.
- Generators are memory-efficient and generate values only when needed.
- Iterate over a generator using `next()` or a `for` loop.
- Useful for custom iterators and processing large or infinite data streams.