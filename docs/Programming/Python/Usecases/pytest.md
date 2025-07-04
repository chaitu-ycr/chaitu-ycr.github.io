# 🧪 pytest: Simple & Powerful Python Testing

**pytest** is a popular Python package for writing and running tests in Python. It makes testing simple, readable, and flexible, supporting test discovery, fixtures, parameterized tests, and exception checks.

---

## 🚀 Installation

```bash
pip install pytest
```

---

## 📝 Writing Simple Tests

Create a file like `test_example.py` and write functions starting with `test_`:

```python
def test_addition():
    assert 1 + 1 == 2

def test_subtraction():
    assert 2 - 1 == 1
```

---

## ▶️ Running Tests

Run all tests in your project folder:

```bash
pytest
```
pytest will auto-discover and run all test files and functions.

---

## 🧰 Fixtures: Reusable Test Data

Fixtures help set up data or state for tests:

```python
import pytest

@pytest.fixture
def sample_list():
    return [1, 2, 3]

def test_sample_list(sample_list):
    assert sum(sample_list) == 6
```

---

## 🔁 Parameterized Tests: Test with Multiple Inputs

Run the same test with different data:

```python
import pytest

@pytest.mark.parametrize("num, expected", [
    (2, True),
    (3, False),
    (10, True),
])
def test_is_even(num, expected):
    assert (num % 2 == 0) == expected
```

---

## ⚠️ Exception Testing: Check for Errors

Test if code raises an expected exception:

```python
import pytest

def test_zero_division():
    with pytest.raises(ZeroDivisionError):
        1 / 0

def test_value_error():
    with pytest.raises(ValueError):
        int("abc")
```

---

## 🏁 Summary

- **pytest** is easy, flexible, and powerful.
- Supports simple tests, fixtures, parameterized tests, and exception checks.
- Helps you catch bugs early and keep your code reliable.

---

## 📝 Practice Questions

1. Write a test for a function that multiplies two numbers.
2. Create a fixture that returns a dictionary and write a test using it.
3. Use `@pytest.mark.parametrize` to test a function that checks if a number is even.
4. Write a test that checks if a `ValueError` is raised when converting a non-numeric string to an integer.
5. Write a parameterized test for a function that returns the square of a number.