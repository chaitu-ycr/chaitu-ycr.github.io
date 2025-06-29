# Multithreading in Python

Multithreading in Python allows you to run multiple threads (smaller units of a process) concurrently, which can be useful for I/O-bound tasks. Here's a high-level overview of how it works:

1. **Thread Creation**: You create a thread by instantiating the `Thread` class from the `threading` module.
2. **Thread Execution**: You start the thread using the `start()` method, which invokes the `run()` method of the thread.
3. **Thread Synchronization**: You can use locks, semaphores, and other synchronization primitives to manage access to shared resources and avoid race conditions.
4. **Thread Termination**: Threads can be joined using the `join()` method, which waits for the thread to complete.

```python
import threading
import time

def print_numbers():
    for i in range(5):
        print(f"Number: {i}")
        time.sleep(1)

def print_letters():
    for letter in 'abcde':
        print(f"Letter: {letter}")
        time.sleep(1)

# Create threads
thread1 = threading.Thread(target=print_numbers)
thread2 = threading.Thread(target=print_letters)

# Start threads
thread1.start()
thread2.start()

# Wait for threads to complete
thread1.join()
thread2.join()

print("Done!")