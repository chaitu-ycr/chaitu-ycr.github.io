# 📝 YAML Guide

YAML (YAML Ain't Markup Language) is a human-readable data serialization format, widely used for configuration files and data exchange.

- 🌐 **Official Site:** [yaml.org](https://yaml.org/)
- 📜 **Specifications:** [Spec 1.2](https://yaml.org/spec/1.2/spec.html), [Spec 1.1](https://yaml.org/spec/1.1/current.html)

> **Note:**  
> - 🧑‍💻 YAML uses spaces (not tabs) for indentation.  
> - 📏 Indentation defines structure and hierarchy.

---

## 📚 Table of Contents

1. [Introduction](#introduction)
2. [Syntax Basics](#syntax-basics)
3. [Scalars](#scalars)
4. [Collections](#collections)
5. [Advanced Features](#advanced-features)
6. [Miscellaneous](#miscellaneous)
7. [YAML in Python](#yaml-in-python)
8. [Quick Reference](#quick-reference)

---

## 1. 🏁 Introduction

YAML is a popular, human-friendly data format for configuration files and data exchange.  
**Key features:**  
- Indentation-based structure (no braces or brackets)
- Supports complex data types (lists, dictionaries, etc.)
- Widely used in DevOps, CI/CD, and programming

---

## 2. 🔤 Syntax Basics

### Indentation & Whitespace

- **Spaces Only:** No tabs allowed.
- **Consistent Indent:** Indentation defines structure.

```yml
key1: value1
key2:
  nestedKey1: nestedValue1
  nestedKey2: nestedValue2
```

**❌ Incorrect (tabs cause errors):**
```yml
key1:
<TAB>nestedKey: value
```

### Comments

- Single-line: `# This is a comment`
- Inline: `name: chaitu-ycr  # Inline comment`

```yml
# This is a comment
name: chaitu-ycr  # Inline comment
```

---

## 3. 🔢 Scalars

Scalars are single values: **strings**, **numbers**, **booleans**, or **null**.

### String Styles

| Style         | Example                        | Notes                        |
|---------------|-------------------------------|------------------------------|
| Plain         | `name: chaitu-ycr`            | Unquoted                     |
| Single Quotes | `text: 'It''s a sunny day'`   | Escape `'` as `''`           |
| Double Quotes | `text: "Hello, \nWorld!"`     | Supports escapes             |
| Emoji         | `emoji: "😀😃😄"`              | Unicode supported            |

#### Multiline Strings

| Style         | Syntax Example         | Preserves Line Breaks? | Description                  |
|---------------|-----------------------|------------------------|------------------------------|
| Block (`|`)   | `block_scalar: | ...` | ✅ Yes                 | Keeps line breaks            |
| Folded (`>`)  | `folded_scalar: > ...`| ❌ No (folds to spaces)| Folds newlines into spaces   |

```yml
block_scalar: |
  This is a block scalar.
  It preserves line breaks.

folded_scalar: >
  This is a folded scalar.
  It folds new lines into spaces,
  creating a single flowing paragraph.
```

#### Special Characters

- Double quotes allow escapes:  
  `special: "Newline: \n, Tab: \t, Quote: \""`

---

### Numbers & Type Tags

| Type         | Example                        | Description                        |
|--------------|-------------------------------|------------------------------------|
| Integer      | `age: 30`                     | Whole number 🔢                    |
| Negative     | `temperature: -5`             | Negative integer ❄️                |
| Float        | `height: 5.9`                 | Decimal number 💧                  |
| Scientific   | `speed: 3.0e8`                | Exponential notation 🚀            |
| Hexadecimal  | `color: 0xFF5733`             | Hex number 🎨                      |
| Octal        | `perm: 0755`                  | File permissions 🗂️                |
| Binary       | `bin: 0b101010`               | Binary number 💾                   |
| Explicit Tag | `!!int "42"`, `!!float "3.14"`| Explicit type tags 🏷️              |

---

### Booleans

| True Values         | False Values        |
|---------------------|--------------------|
| `true` ✅, `yes` 👍, `on` 🔛 | `false` ❌, `no` 👎, `off` 🔇 |

```yml
is_active: true
has_license: false
is_enabled: yes
is_disabled: no
light_switch: on
dark_mode: off
```

---

### Null

| Representation         | Example                        |
|-----------------------|--------------------------------|
| Explicit `null`       | `preferred_language: null`     |
| Tilde (`~`)           | `shipping_address: ~`          |
| Empty Value           | `phone_number:`                |
| Empty Quotes          | `additional_info: ''`          |

---

## 4. 📦 Collections

### Sequences (Lists)

```yml
fruits:
  - 🍏 Apple
  - 🍌 Banana
  - 🍒 Cherry

mixed_list:
  - "String"
  - 42
  - true
  - null
```

- **Nested lists, lists of dictionaries, and empty lists (`[]`) are supported.**

### Mappings (Dictionaries)

```yml
person:
  name: chaitu-ycr
  age: 30

address: {street: 123 Main St, city: chennai, zip: 12345}
empty_mapping: {}
```

- **Nested mappings, inline mappings, and empty mappings (`{}`) are supported.**

---

## 5. 🛠️ Advanced Features

### Anchors & Aliases

```yml
defaults: &defaults
  country: 🇮🇳 INDIA
  currency: 💸 RUPEE

location1:
  <<: *defaults
  city: chennai
```

### Complex Keys

```yml
? [first, second]
: "Tuple as a key"
```

### Multi-Document Files

```yml
---
document1:
  key1: value1
---
document2:
  key2: value2
...
```

---

## 6. 🧩 Miscellaneous

### Date and Time

```yml
birth_date: 1990-12-31
meeting_time: 14:30:00
event_timestamp: 2023-04-06T14:30:00Z
local_timestamp: 2023-04-06T14:30:00+05:30
date_range: "2023-04-01 to 2023-04-07"
time_range: "14:30:00 to 15:30:00"
```

### Custom Data Types

```yml
!color
name: Blue
code: "#0000FF"
```

---

## 7. 🐍 YAML in Python

### Install PyYAML

```sh
pip install pyyaml
```

### Read YAML

```python
import yaml

def read_yaml(file_path):
    with open(file_path, 'r') as file:
        data = yaml.safe_load(file)
    return data

data = read_yaml('example.yaml')
print(data)
```

### Write YAML

```python
import yaml

data = {
    'name': 'chaitu-ycr',
    'age': 30,
    'address': {
        'street': '123 Main St',
        'city': 'chennai',
        'zip': 12345
    },
    'hobbies': ['Reading', 'Hiking', 'Coding']
}

def write_yaml(file_path, data):
    with open(file_path, 'w') as file:
        yaml.dump(data, file, default_flow_style=False)

write_yaml('output.yaml', data)
```

**Sample Output (`output.yaml`):**
```yml
name: chaitu-ycr
age: 30
address:
  street: 123 Main St
  city: chennai
  zip: 12345
hobbies:
- Reading
- Hiking
- Coding
```

---

## 8. 🗂️ Quick Reference

- **Indentation:** Use spaces, not tabs.
- **Comments:** Start with `#`.
- **Strings:** Plain, single-quoted, double-quoted, multiline (`|` or `>`).
- **Numbers:** Integer, float, hex, octal, binary.
- **Booleans:** `true`/`false`, `yes`/`no`, `on`/`off`.
- **Null:** `null`, `~`, empty value, `''`.
- **Lists:** Use `-` for each item.
- **Dictionaries:** `key: value` pairs.
- **Anchors/Aliases:** `&anchor`, `*alias`.
- **Multi-document:** Separate with `---`.