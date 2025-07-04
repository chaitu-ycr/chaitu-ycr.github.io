# 🤖 Gradio

**Gradio** is a Python library that makes it super easy to create web interfaces for your machine learning models, data functions, or simple apps. No web development skills needed—just write your function and let Gradio handle the rest!

---

## 🚀 What Can You Do with Gradio?

### 🧑‍💻 1. Model Demos
Showcase ML models (like image classifiers or text generators) interactively.

```python
import gradio as gr

def greet(name):
    return f"Hello, {name}!"

gr.Interface(fn=greet, inputs="text", outputs="text").launch()
```

---

### 🛠️ 2. Data Apps & Tools
Build quick tools (calculators, converters, etc.) with your own functions.

```python
def add(a, b):
    return a + b

gr.Interface(fn=add, inputs=["number", "number"], outputs="number").launch()
```

---

### 📊 3. Visualize Data
Display images, audio, or plots interactively.

```python
import matplotlib.pyplot as plt
import numpy as np

def plot_sin(freq):
    x = np.linspace(0, 2 * np.pi, 100)
    y = np.sin(freq * x)
    fig, ax = plt.subplots()
    ax.plot(x, y)
    return fig

gr.Interface(fn=plot_sin, inputs=gr.Slider(1, 10), outputs="plot").launch()
```

---

### 🌐 4. Share Your App
Easily share your app with a public link.

```python
gr.Interface(fn=greet, inputs="text", outputs="text").launch(share=True)
```

---

### 🧩 5. Multiple Inputs & Outputs
Support for various input/output types (text, image, audio, etc.).

```python
def process(text, img):
    return text.upper(), img

gr.Interface(
    fn=process,
    inputs=["text", "image"],
    outputs=["text", "image"]
).launch()
```

---

**Tip:** Focus on your function—Gradio takes care of the interface!
See [Gradio Documentation](https://gradio.app/docs/) for more.

---

## 📝 Practice Questions

1. Write a Gradio interface for a function that reverses a string.
2. Build a calculator app that supports add, subtract, multiply, and divide.
3. Make a demo that takes an image and returns its grayscale version.
4. How do you share your Gradio app with someone outside your local network?
5. Modify an example to accept both text and number inputs and display both outputs.
