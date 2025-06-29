# 🧮 Python `array` Module

The `array` module provides a memory-efficient, fixed-size, homogeneous data structure for storing large collections of primitive numerical data types. It is built-in and useful when you need efficient storage and manipulation of numbers, but is less flexible than Python lists and less feature-rich than NumPy arrays.

---

## ✨ Key Features

| Feature             | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| **Memory Efficient**| Uses less memory than lists for large collections of numbers                |
| **Fixed Size**      | Size is defined at creation and cannot be resized                           |
| **Homogeneous Data**| All elements must be of the same data type, specified by a typecode         |
| **Fast Operations** | Faster than lists for certain numerical operations                          |

---

## 🔤 Common Typecodes

| Typecode | C Type         | Python Type | Description          | Example Values      |
|----------|----------------|-------------|----------------------|---------------------|
| `'b'`    | signed char    | int         | Signed integer       | -128, 0, 127        |
| `'B'`    | unsigned char  | int         | Unsigned integer     | 0, 255              |
| `'h'`    | signed short   | int         | Short integer        | -32768, 32767       |
| `'H'`    | unsigned short | int         | Unsigned short       | 0, 65535            |
| `'i'`    | signed int     | int         | Integer              | -2147483648, 2147483647 |
| `'I'`    | unsigned int   | int         | Unsigned integer     | 0, 4294967295       |
| `'l'`    | signed long    | int         | Long integer         | Platform dependent  |
| `'L'`    | unsigned long  | int         | Unsigned long        | Platform dependent  |
| `'f'`    | float          | float       | Floating point       | 1.0, -2.5           |
| `'d'`    | double         | float       | Double precision     | 1.0, -2.5           |

---

## 🛠️ Creating Arrays

```python
from array import array

# Array of signed integers
int_array = array('i', [1, 2, 3, 4])

# Array of floats
float_array = array('f', [1.5, 2.3, 4.1])

# Array of unsigned bytes
byte_array = array('B', [10, 20, 30, 255])
```

---

## 🔍 Accessing and Modifying Elements

```python
# Access elements by index
print(int_array[0])  # Output: 1

# Modify elements by assignment
int_array[1] = 10
print(int_array)  # Output: array('i', [1, 10, 3, 4])

# Arrays are fixed-size; you cannot change their length after creation.
```

---

## 🧰 Common Methods

| Method                | Description                                              |
|-----------------------|---------------------------------------------------------|
| `append(x)`           | Add an element to the end (not efficient for large arrays) |
| `extend(iterable)`    | Appends items from iterable                             |
| `insert(i, x)`        | Inserts `x` at position `i`                             |
| `pop([i])`            | Removes and returns item at index `i` (default last)    |
| `remove(x)`           | Removes first occurrence of `x`                         |
| `reverse()`           | Reverses the array in place                             |
| `count(x)`            | Counts occurrences of `x`                               |
| `index(x)`            | Returns index of first occurrence of `x`                |
| `tolist()`            | Converts array to a Python list                         |
| `tobytes()`           | Returns a bytes representation of the array             |
| `frombytes(s)`        | Loads array from bytes                                  |
| `fromfile(file, n)`   | Reads `n` elements from a file                          |
| `buffer_info()`       | Returns (address, length) of the buffer                 |
| `byteswap()`          | Swaps byte order (useful for endianness)                |

**Examples:**

```python
# Append and extend
int_array.append(5)
int_array.extend([6, 7])

# Remove and pop
int_array.remove(3)
last = int_array.pop()

# Convert to list
lst = int_array.tolist()
```

---

## 📊 Array vs List vs NumPy

| Feature          | `array` module | `list`      | `numpy.ndarray` |
|------------------|---------------|-------------|-----------------|
| Homogeneous      | ✅            | ❌          | ✅              |
| Fixed size       | ✅            | ❌          | ✅ (mostly)     |
| Memory efficient | ✅            | ❌          | ✅              |
| Fast math ops    | ❌            | ❌          | ✅              |
| Advanced features| ❌            | ❌          | ✅              |

---

## 🧑‍💻 When to Use the `array` Module

- For memory-efficient storage of large collections of primitive numerical data types.
- When you need homogeneous, fixed-size arrays and do not require advanced numerical operations.
- Not recommended for frequent resizing or mixed data types—use lists or NumPy arrays instead.

---

## 📝 Additional Notes

- The `array` module is built-in but less commonly used than lists or NumPy arrays.
- For most data science and numerical computing tasks, **NumPy arrays** are preferred due to their advanced features and performance.
