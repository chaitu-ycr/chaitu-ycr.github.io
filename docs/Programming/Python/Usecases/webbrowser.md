# 🌐 webbrowser

The `webbrowser` module in Python lets you easily open web pages in your default browser from your code. It's handy for automating tasks like launching URLs, documentation, or web apps. It works on all major platforms.

---

## 🚀 Common Use Cases

### 1. 🔗 Open a URL in the default browser

```python
import webbrowser

webbrowser.open('https://www.python.org')
```

---

### 2. 🪟 Open a URL in a new browser window

```python
import webbrowser

webbrowser.open_new('https://www.python.org')
```

---

### 3. 🗂️ Open a URL in a new browser tab

```python
import webbrowser

webbrowser.open_new_tab('https://www.python.org')
```

---

### 4. 🦊 Open a URL with a specific browser

```python
import webbrowser

firefox = webbrowser.get('firefox')  # or use 'chrome', 'windows-default', etc.
firefox.open('https://www.python.org')
```

---

### 5. 🛠️ Register and use a custom browser

```python
import webbrowser

webbrowser.register('mybrowser', None, webbrowser.BackgroundBrowser("C://Path//to//browser.exe"))
webbrowser.get('mybrowser').open('https://www.python.org')
```

---

### 6. 📄 Open a local HTML file

```python
import webbrowser

webbrowser.open('file:///C:/path/to/your/file.html')
```

---

**Note:**
- `webbrowser` is simple and cross-platform, but not for advanced automation (use `selenium` for that).
- If you use an invalid browser name, Python will raise a `webbrowser.Error`.

---

## 📝 Practice Questions

1. Write a script to open three different websites in new tabs.
2. How would you open a URL using Firefox specifically?
3. Register a custom browser and use it to open a webpage.
4. What happens if you try to open a URL with an invalid browser name?
5. Modify the script to open a local HTML file in your browser.
