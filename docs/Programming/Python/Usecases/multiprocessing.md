# ⚡ Python `multiprocessing` Package

The `multiprocessing` module lets you run multiple processes in parallel, making it perfect for CPU-bound tasks. Each process has its own Python interpreter and memory space, allowing you to fully utilize your CPU cores.

---

## 🚀 Main Use Cases

### 👷‍♂️ Create and Run Processes
Start new processes using the `Process` class.

```python
import multiprocessing
import os

def show_pid():
    print(f'Process ID: {os.getpid()}')

if __name__ == '__main__':
    processes = [multiprocessing.Process(target=show_pid) for _ in range(3)]
    for p in processes: p.start()
    for p in processes: p.join()
```

---

### 🔄 Share Data Between Processes

#### Using `Queue`
Share data safely between processes.

```python
import multiprocessing

def worker(q):
    q.put('Hello from worker!')

if __name__ == '__main__':
    q = multiprocessing.Queue()
    p = multiprocessing.Process(target=worker, args=(q,))
    p.start(); p.join()
    print(q.get())
```

#### Using Shared Memory (`Value`)
Share simple data types.

```python
import multiprocessing

def increment(val):
    val.value += 1

if __name__ == '__main__':
    val = multiprocessing.Value('i', 0)
    procs = [multiprocessing.Process(target=increment, args=(val,)) for _ in range(5)]
    for p in procs: p.start()
    for p in procs: p.join()
    print(f'Final value: {val.value}')
```

---

### 🏊 Task Distribution with `Pool`
Distribute tasks among worker processes.

```python
import multiprocessing

def factorial(n):
    return 1 if n == 0 else n * factorial(n-1)

if __name__ == '__main__':
    with multiprocessing.Pool(4) as pool:
        results = pool.map(factorial, range(1, 6))
    print(results)
```

---

### 🔗 Process Communication with `Pipe`
Send data between two processes.

```python
import multiprocessing

def sender(conn):
    conn.send('Message from sender!')

def receiver(conn):
    print(conn.recv())

if __name__ == '__main__':
    parent, child = multiprocessing.Pipe()
    p1 = multiprocessing.Process(target=sender, args=(child,))
    p2 = multiprocessing.Process(target=receiver, args=(parent,))
    p1.start(); p2.start()
    p1.join(); p2.join()
```

---

### 🔒 Synchronize with Locks
Prevent race conditions with locks.

```python
import multiprocessing

def safe_increment(lock, val):
    with lock:
        val.value += 1

if __name__ == '__main__':
    lock = multiprocessing.Lock()
    val = multiprocessing.Value('i', 0)
    procs = [multiprocessing.Process(target=safe_increment, args=(lock, val)) for _ in range(5)]
    for p in procs: p.start()
    for p in procs: p.join()
    print(f'Final value: {val.value}')
```

---

## 📝 Practice Questions

1. 👷‍♂️ Create 3 processes, each printing its process ID.
2. 🔄 Use `Value` to let multiple processes increment a shared counter.
3. 🏊 Use `Pool` to calculate the factorial of numbers from 1 to 10.
4. 🔗 Use `Pipe` for one process to send a message to another.
5. 🔒 Use a lock to let multiple processes safely update a shared list.
