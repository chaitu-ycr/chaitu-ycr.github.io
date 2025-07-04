# ✨ customtkinter: Modern Tkinter GUIs

## 🧩 What is customtkinter?
`customtkinter` is a Python library that upgrades the classic `tkinter` GUI toolkit. It offers modern, stylish, and highly customizable widgets, making your apps look fresh and professional with minimal effort.

---

## 🚀 Common Use Cases & Examples

### 🔘 Modern Buttons
Create buttons with custom colors and hover effects.
```python
import customtkinter as ctk

app = ctk.CTk()
button = ctk.CTkButton(app, text="Click Me", fg_color="blue", hover_color="lightblue")
button.pack(pady=20)
app.mainloop()
```

---

### 📝 Stylish Entry Fields
Add input fields with placeholder text and modern styling.
```python
import customtkinter as ctk

app = ctk.CTk()
entry = ctk.CTkEntry(app, placeholder_text="Enter your name")
entry.pack(pady=20)
app.mainloop()
```

---

### 🔄 Toggle Switches
Use switches for on/off settings.
```python
import customtkinter as ctk

app = ctk.CTk()
switch = ctk.CTkSwitch(app, text="Enable Feature")
switch.pack(pady=20)
app.mainloop()
```

---

### 🎚️ Sliders
Let users pick values with interactive sliders.
```python
import customtkinter as ctk

app = ctk.CTk()
slider = ctk.CTkSlider(app, from_=0, to=100)
slider.pack(pady=20)
app.mainloop()
```

---

### 🗂️ Custom Frames
Organize your widgets using stylish frames.
```python
import customtkinter as ctk

app = ctk.CTk()
frame = ctk.CTkFrame(app, width=200, height=100, corner_radius=10)
frame.pack(pady=20)
app.mainloop()
```

---

### 📊 Progress Bars
Show progress with modern indicators.
```python
import customtkinter as ctk

app = ctk.CTk()
progress = ctk.CTkProgressBar(app)
progress.pack(pady=20)
progress.set(0.5)  # 50% progress
app.mainloop()
```

---

## 💡 Key Points
- Modern look for classic tkinter GUIs.
- Widgets are easy to customize.
- Great for quick, attractive Python apps.

---

## 📝 Practice Questions

1. Build a GUI with a button and entry field. Show the entered text when the button is clicked.
2. Make a settings panel with toggle switches for features.
3. Create a slider app to adjust a value (like brightness).
4. Add a progress bar that updates as the user interacts.
5. Use frames to neatly organize multiple widgets in one window.
