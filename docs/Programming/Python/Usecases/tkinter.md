# 🖼️ Tkinter Introduction

Tkinter is Python’s built-in library for creating simple GUI (Graphical User Interface) applications. It’s easy to use and comes pre-installed with Python.

---

## 🧩 Key Concepts

- **Widgets**: Building blocks like `Label`, `Button`, `Entry`, `Text`, and `Frame`.
- **Geometry Managers**: Control widget placement using `pack()`, `grid()`, or `place()`.
- **Event Handling**: Respond to user actions (like button clicks).

---

## 🏗️ Basic Example

```python
import tkinter as tk

root = tk.Tk()
root.title("Hello Tkinter")

label = tk.Label(root, text="Welcome!")
label.pack()

def change_text():
    label.config(text="Button Clicked!")

button = tk.Button(root, text="Click Me", command=change_text)
button.pack()

root.mainloop()
```

---

## 🧱 Widgets Examples

### 1. Label & Entry

```python
import tkinter as tk

root = tk.Tk()
tk.Label(root, text="Name:").pack()
entry = tk.Entry(root)
entry.pack()
root.mainloop()
```

### 2. Button & Event Handling

```python
import tkinter as tk

def greet():
    print("Hello!")

root = tk.Tk()
tk.Button(root, text="Greet", command=greet).pack()
root.mainloop()
```

### 3. Text Widget

```python
import tkinter as tk

root = tk.Tk()
text = tk.Text(root, height=3, width=20)
text.pack()
root.mainloop()
```

### 4. Frame (Grouping Widgets)

```python
import tkinter as tk

root = tk.Tk()
frame = tk.Frame(root)
frame.pack()
tk.Label(frame, text="Inside Frame").pack()
tk.Button(frame, text="OK").pack()
root.mainloop()
```

---

## 📐 Geometry Managers

### pack()

```python
import tkinter as tk

root = tk.Tk()
tk.Label(root, text="Top").pack(side="top")
tk.Label(root, text="Bottom").pack(side="bottom")
root.mainloop()
```

### grid()

```python
import tkinter as tk

root = tk.Tk()
tk.Label(root, text="Row 0, Col 0").grid(row=0, column=0)
tk.Label(root, text="Row 1, Col 1").grid(row=1, column=1)
root.mainloop()
```

### place()

```python
import tkinter as tk

root = tk.Tk()
tk.Label(root, text="Placed").place(x=50, y=50)
root.mainloop()
```

---

## 📝 Practice Questions

1. Create a window with two buttons: "Greet" and "Exit". "Greet" should print a message, "Exit" should close the window.
2. Make a simple login form with `Entry` widgets for username and password.
3. Use the `grid()` manager to arrange three labels and three entry fields in a form layout.
4. Add a `Text` widget and a button. When the button is clicked, display the text entered in the console.
5. Group two buttons inside a `Frame` and place the frame at the bottom of the window.
