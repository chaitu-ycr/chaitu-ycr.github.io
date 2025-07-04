# 📁 File Handling in Python

File handling lets you read, write, update, and manage files in Python. It's useful for saving data, logging, and working with external files.

---

## 🛠️ Common Use Cases

### 📖 1. Reading a File
Read the whole content of a file.

```python
with open('example.txt', 'r') as file:
    content = file.read()
    print(content)
```

---

### ✍️ 2. Writing to a File
Write data to a file (overwrites existing content).

```python
with open('example.txt', 'w') as file:
    file.write('Hello, World!')
```

---

### ➕ 3. Appending to a File
Add data to the end of a file.

```python
with open('example.txt', 'a') as file:
    file.write('\nNew line added.')
```

---

### 📄 4. Reading File Line by Line
Process each line separately.

```python
with open('example.txt', 'r') as file:
    for line in file:
        print(line.strip())
```

---

### 🖼️ 5. Working with Binary Files
Read or write non-text files (like images).

```python
with open('image.png', 'rb') as file:
    data = file.read()
```

```python
with open('copy.png', 'wb') as file:
    file.write(data)
```

---

### 🔍 6. Checking if a File Exists
Check if a file is present.

```python
import os
if os.path.exists('example.txt'):
    print('File exists!')
```

---

### 🗑️ 7. Deleting a File
Remove a file from the system.

```python
import os
if os.path.exists('example.txt'):
    os.remove('example.txt')
    print('File deleted!')
```

---

## 📝 Practice Questions

1. Read a file and print only lines containing the word "Python".
2. Create a file and write numbers 1 to 10, each on a new line.
3. Append your name to an existing file.
4. Check if a file exists before reading it.
5. Delete a file only if it exists.
6. Copy an image file using binary mode.
