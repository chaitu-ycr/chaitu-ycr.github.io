# 🧵 Python Multithreading Made Simple

Python’s `threading` module lets you run code in parallel threads—great for I/O-bound tasks like file, network, or database operations. It’s not ideal for CPU-heavy work (due to the GIL), but it’s perfect for speeding up waiting tasks.

---

## 🚦 Main Use Cases

### 1️⃣ Create and Start Threads

```python
import threading

def greet():
    print("Hello from a thread!")

thread = threading.Thread(target=greet)
thread.start()
thread.join()
```

---

### 2️⃣ Custom Thread Classes

```python
import threading

class MyThread(threading.Thread):
    def run(self):
        print("Custom thread running!")

thread = MyThread()
thread.start()
thread.join()
```

---

### 3️⃣ Synchronize Threads 🛡️

Use a `Lock` to safely update shared data.

```python
import threading

lock = threading.Lock()
counter = 0

def safe_increment():
    global counter
    with lock:
        counter += 1
        print(counter)

threads = [threading.Thread(target=safe_increment) for _ in range(5)]
for t in threads: t.start()
for t in threads: t.join()
```

---

### 4️⃣ Wait for Threads to Finish ⏳

```python
import threading
import time

def task():
    time.sleep(1)
    print("Task done!")

thread = threading.Thread(target=task)
thread.start()
print("Waiting...")
thread.join()
print("Thread finished!")
```

---

### 5️⃣ Daemon Threads 👻

Daemon threads run in the background and exit when the main program ends.

```python
import threading
import time

def background():
    while True:
        print("Background work...")
        time.sleep(1)

t = threading.Thread(target=background, daemon=True)
t.start()
time.sleep(3)
print("Main program done!")
```

---

### 6️⃣ Thread Pooling 🚀

Use `ThreadPoolExecutor` for easy thread management.

```python
from concurrent.futures import ThreadPoolExecutor

def square(n):
    return n * n

with ThreadPoolExecutor(max_workers=3) as pool:
    results = pool.map(square, [1, 2, 3, 4, 5])
    print(list(results))
```

---

### 7️⃣ File Writing with Lock 📝

Safely write to a file from multiple threads.

```python
import threading

lock = threading.Lock()

def write_to_file(text):
    with lock, open("output.txt", "a") as f:
        f.write(text + "\n")

threads = [threading.Thread(target=write_to_file, args=(f"Line {i}",)) for i in range(5)]
for t in threads: t.start()
for t in threads: t.join()
```

---

**Summary:**  
- Use threads for I/O-bound tasks.
- Always use locks for shared data.
- Daemon threads are for background tasks.
- Use thread pools for managing multiple threads easily.

---

## 📝 Practice Questions

1. 🟢 Create two threads: one prints even numbers, the other prints odd numbers up to 10.
2. 🔒 Implement a thread-safe counter using a `Lock`.
3. 👻 Write a daemon thread that logs a message every second while the main program runs for 5 seconds.
4. 🚀 Use `ThreadPoolExecutor` to calculate factorials for a list of numbers.
5. 📝 Write a program where multiple threads safely write to a shared file using a `Lock`.
