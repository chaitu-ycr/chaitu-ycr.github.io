# Multiprocessing in Python

Multiprocessing in Python allows you to create multiple processes, each with its own Python interpreter and memory space. This is particularly useful for CPU-bound tasks, as it can take advantage of multiple CPU cores to perform tasks in parallel, thereby improving performance.

Here's a step-by-step explanation of how multiprocessing works in Python:

1. **Import the `multiprocessing` module**: This module provides the necessary functions and classes to create and manage processes.

2. **Create a `Process` object**: You can create a new process by instantiating the `Process` class and passing the target function and its arguments.

3. **Start the process**: Use the `start()` method to start the execution of the process.

4. **Wait for the process to complete**: Use the `join()` method to wait for the process to finish its execution.

5. **Share data between processes**: You can use `Queue`, `Pipe`, or shared memory objects like `Value` and `Array` to share data between processes.

```python
import multiprocessing
import time

def worker(num):
    """Thread worker function"""
    print(f'Worker: {num}')
    time.sleep(2)
    print(f'Worker {num} finished')

if __name__ == '__main__':
    processes = []
    for i in range(5):
        p = multiprocessing.Process(target=worker, args=(i,))
        processes.append(p)
        p.start()

    for p in processes:
        p.join()

    print('All processes finished.')