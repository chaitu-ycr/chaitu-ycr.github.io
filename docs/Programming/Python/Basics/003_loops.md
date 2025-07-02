# 🔁 Loops in Python

Loops are fundamental for repeating actions in Python. The two main types are `for` and `while` loops. Python also provides control flow statements like `break`, `continue`, and `pass` to manage loop execution.

## 🌀 1. For Loops

A `for` loop iterates over sequences (like lists, tuples, or strings) and executes a block of code for each item.

### ▶️ Basic for Loop

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```
- Iterates over the `fruits` list, printing each fruit.

### 🔢 Looping with Index

```python
numbers = [1, 2, 3, 4]
for index, number in enumerate(numbers):
    print(f"Index: {index}, Number: {number}")
```
- Uses `enumerate()` to get both index and value in each iteration.

### 📏 Looping over a Range

```python
for i in range(5):  # Range from 0 (inclusive) to 5 (exclusive)
    print(i)
```
- `range(n)` generates numbers from 0 to n-1.

### 🧩 For-Else Loop

```python
for number in range(10):
    if number == 5:
        print("Number 5 found in the list!")
        break
else:
    print("Number 5 not found.")
```
- The `else` clause runs only if the loop completes without a `break`.

## 🔄 2. While Loops

A `while` loop repeatedly executes a block of code as long as a condition is true.

```python
count = 0
while count < 5:
    print("Count:", count)
    count += 1  # Increment count by 1
```
- Runs as long as `count < 5`, printing and incrementing `count` each time.

## 🛑 3. Control Flow Statements

| Statement  | Description                            | Example                      |
|------------|----------------------------------------|------------------------------|
| `break`    | Exit the loop immediately              | `if x == 5: break`           |
| `continue` | Skip the rest of the current iteration | `if x % 2 == 0: continue`    |
| `pass`     | Do nothing (placeholder)               | `for x in range(5): pass`    |

### 🚪 break

- Exits the loop immediately.

```python
for number in range(10):
    if number == 5:
        print("Found 5, breaking out of the loop!")
        break
    print(number)
```
- Prints numbers 0 to 4, then breaks when 5 is found.

### ⏭️ continue

- Skips the current iteration and moves to the next.

```python
for number in range(10):
    if number % 2 == 0:  # Skip even numbers
        continue
    print(number)
```
- Prints only odd numbers (1, 3, 5, 7, 9).

### ⏸️ pass

- Does nothing; acts as a placeholder.

```python
for number in range(5):
    pass  # Placeholder, no action
print("Loop finished!")
```

## 📝 5. Summary Table

| Loop Type   | Use Case                                 | Example Syntax                |
|-------------|------------------------------------------|-------------------------------|
| `for`       | Iterate over sequences                   | `for item in sequence:`       |
| `while`     | Repeat as long as a condition is `True`  | `while condition:`            |
| `break`     | Exit the loop                            | `break`                       |
| `continue`  | Skip to next iteration                   | `continue`                    |
| `pass`      | Placeholder, does nothing                | `pass`                        |

Use these constructs to control the flow of your programs efficiently! 🚀

## 🧪 Practice Exercises

1. Create a program that prints numbers from 1 to 20, but skips multiples of 3.
2. Write a function that takes a list of names and prints each name with its length.
3. Implement a countdown timer using a `while` loop that counts down from 10 to 0, printing each number.
4. Create a program that finds the first even number in a list and breaks out of the loop when found.
5. Write a program that uses a `for` loop to calculate the factorial of a number provided by the user.
6. Implement a program that prints the Fibonacci sequence up to a specified number using a `while` loop.
