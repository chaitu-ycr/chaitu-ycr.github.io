# 🐍 Python Regular Expressions

Python’s `re` module lets you find, match, split, and replace patterns in text using regular expressions. It’s great for searching, validating, and cleaning up strings.

---

## 🔑 Key Syntax

- `.` any character except newline
- `^` start of string
- `$` end of string
- `*` 0 or more times
- `+` 1 or more times
- `?` 0 or 1 time
- `{m,n}` between m and n times

---

## ⚡ Main Functions & Examples

```python
import re

text = "There are 123 apples and 456 oranges."

# 1️⃣ Find all matches
print(re.findall(r'\d+', text))  # ['123', '456']

# 2️⃣ Search for first match anywhere
print(re.search(r'apples', text).group())  # 'apples'

# 3️⃣ Match at the start
print(re.match(r'There', text).group())  # 'There'

# 4️⃣ Replace pattern
print(re.sub(r'\d+', '#', text))  # 'There are # apples and # oranges.'

# 5️⃣ Split by pattern
print(re.split(r'\s+', text))  # ['There', 'are', '123', 'apples', 'and', '456', 'oranges.']

# 6️⃣ Groups: capture parts of a match
print(re.findall(r'(\d+)\s(apples|oranges)', text))  # [('123', 'apples'), ('456', 'oranges')]

# 7️⃣ Compile for reuse
pattern = re.compile(r'\d+')
print(pattern.findall(text))  # ['123', '456']

# 8️⃣ Validate input (e.g., email)
email = "test@example.com"
print(bool(re.fullmatch(r'\w+@\w+\.\w+', email)))  # True
```

---

## 📝 Practice Questions

1. Write a regex to find all words starting with 'a' in a sentence.
2. Replace all vowels in a string with '*'.
3. Extract all numbers from: "Order 12 apples, 5 bananas, and 30 oranges."
4. Validate if a string is a valid phone number (e.g., 123-456-7890).
5. Split a sentence into words, ignoring punctuation.
