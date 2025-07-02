# 📝 Python Lists

Lists are a fundamental data structure in Python used to store collections of items in an **ordered** and **changeable** way.

## 📦 Creating Lists

- Use square brackets `[]` and separate items with commas.
- Lists can contain items of different data types (strings, integers, floats, booleans, even other lists).

```python
fruits = ["🍎", "🍌", "🍒"]
numbers = [1, 2, 3, 4.5]
mixed_list = ["hello", 10, True]
empty_list = []
nested_list = [[1, 2], [3, 4]]
```

## 🔎 Accessing Elements

- Elements are indexed starting from 0.
- Use negative indexing to access elements from the end (`-1` is the last element).

| Indexing Type   | Example         | Result   |
|-----------------|----------------|----------|
| Positive Index  | `fruits[1]`    | `"🍌"`   |
| Negative Index  | `fruits[-1]`   | `"🍒"`   |

```python
first_fruit = fruits[0]      # "🍎"
last_number = numbers[-1]    # 4.5
```

## ✂️ Slicing Lists

- Extract a portion of a list using `[start:end:step]`.

| Syntax          | Description                | Example           | Result                |
|-----------------|---------------------------|-------------------|-----------------------|
| `list[1:3]`     | Elements at 1 and 2       | `fruits[1:3]`     | `["🍌", "🍒"]`         |
| `list[::2]`     | Every second element      | `fruits[::2]`     | `["🍎", "🍒"]`         |
| `list[::-1]`    | Reverse the list          | `fruits[::-1]`    | `["🍒", "🍌", "🍎"]`    |

## 🛠️ Modifying Lists

- Lists are **mutable** (can be changed after creation).
- Assign a new value to an element using its index.

| Method                | Description                          |
|-----------------------|--------------------------------------|
| `append(x)`           | Add `x` to the end                   |
| `insert(i, x)`        | Insert `x` at index `i`              |
| `fruits[i] = x`       | Replace element at index `i`         |

```python
fruits.append("🥭")      # Add to end
fruits.insert(1, "🥑")   # Insert at index 1
fruits[1] = "🥭"         # Replace element at index 1
```

## 🗑️ Removing Elements

| Method                | Description                          |
|-----------------------|--------------------------------------|
| `remove(x)`           | Remove first occurrence of `x`       |
| `pop([i])`            | Remove and return element at index `i` (last by default) |
| `clear()`             | Remove all elements                  |
| `del list[i]`         | Delete element at index `i`          |

```python
fruits.remove("🍒")
fruits.pop()
fruits.clear()
del fruits[0]
```

## 📋 Copying and Extending Lists

| Method                | Description                          |
|-----------------------|--------------------------------------|
| `copy()`              | Returns a shallow copy               |
| `extend(iterable)`    | Appends all elements from another iterable |
| `list1 + list2`       | Concatenate lists                    |

```python
fruits_copy = fruits.copy()
fruits_copy.extend(["🍊", "🍋"])
combined = fruits + numbers
```

## ➕ List Operations

| Operation             | Example                | Result/Description      |
|-----------------------|------------------------|------------------------|
| Length                | `len(fruits)`          | Number of items        |
| Membership            | `"🥭" in fruits`        | `True`/`False`         |
| Concatenation         | `fruits + numbers`     | New combined list      |
| Repetition            | `fruits * 2`           | Repeat list            |

## 🧰 Useful List Methods

| Method                | Description                          |
|-----------------------|--------------------------------------|
| `index(x[, i[, j]])`  | Index of first occurrence of `x`     |
| `count(x)`            | Number of occurrences of `x`         |
| `reverse()`           | Reverse list in place                |
| `sort()`              | Sort list in place                   |

```python
fruits.index("🍎")
fruits.count("🍒")
fruits.reverse()
fruits.sort()
```

## 🧮 List Comprehensions

- Compact way to create lists.

```python
squares = [i**2 for i in range(10)]
evens = [x for x in range(20) if x % 2 == 0]
```

## 🔁 Traversing Lists

```python
for fruit in fruits:
    print(fruit)
```

## 🔃 Sorting Lists

- `sort()` sorts in place
- Use `reverse=True` for descending order
- Use `key` for custom sorting

```python
from random import randint

random_numbers = [randint(0, 100) for _ in range(10)]
random_numbers.sort()
random_numbers.sort(reverse=True)
random_numbers.sort(key=lambda x: x % 10)  # Sort by last digit
```

## 🗂️ Nested Lists

- Lists can contain other lists (useful for matrices, grids, etc.)

```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
print(matrix[1][2])  # 6
```

## 📝 Key Points

- Lists are versatile and can store various data types.
- Indexing and slicing provide flexible access to elements.
- Lists are mutable and support many methods for manipulation.
- List comprehensions offer concise ways to create new lists.
- Nested lists allow for multi-dimensional data storage.

## 🧪 Practice Exercises

1. Create a list of your favorite movies and print each movie.
2. Write a program that takes a list of numbers and returns a new list with only the even numbers.
3. Implement a function that takes a list of strings and returns a new list with the lengths of each string.
4. Create a nested list representing a 3x3 grid and print each row.
5. Write a program that sorts a list of names alphabetically and prints the sorted list.
6. Create a list of random integers and find the maximum and minimum values in the list.
7. Implement a function that takes a list of integers and returns the sum of all elements.
8. Create a program that merges two lists into one, removing duplicates.
9. Write a function that takes a list of numbers and returns a new list with the squares of each number.
10. Create a program that checks if a given item is in a list and prints its index if found.
