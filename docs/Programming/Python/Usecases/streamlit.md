# 🚀 Streamlit

**Streamlit** is a Python library for building interactive web apps for data science and machine learning—fast, with minimal code.

---

## 🎯 Main Use Cases

### 📊 1. Data Display & Visualization
Show dataframes and charts easily.

```python
import streamlit as st
import pandas as pd

df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})
st.write("DataFrame:", df)
st.line_chart(df)
```

---

### 📝 2. User Input Widgets
Collect user input with text boxes, sliders, etc.

```python
import streamlit as st

name = st.text_input("Your name:")
age = st.slider("Your age:", 0, 100, 25)
st.write(f"Hello, {name}! Age: {age}")
```

---

### 📁 3. File Upload
Let users upload files for processing.

```python
import streamlit as st
import pandas as pd

file = st.file_uploader("Upload CSV")
if file:
    df = pd.read_csv(file)
    st.write(df.head())
```

---

### 🖼️ 4. Media Display (Images, Audio, Video)
Show images, play audio, or display videos.

```python
import streamlit as st

st.image("https://placekitten.com/200/300", caption="Kitten")
st.audio("https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3")
st.video("https://www.w3schools.com/html/mov_bbb.mp4")
```

---

### 🏗️ 5. Layouts & Organization
Arrange your app with columns, expanders, etc.

```python
import streamlit as st

col1, col2 = st.columns(2)
col1.write("Left column")
col2.write("Right column")

with st.expander("More info"):
    st.write("Hidden content")
```

---

### ⚡ 6. Caching
Speed up your app by caching functions.

```python
import streamlit as st

@st.cache_data
def slow_fn(x):
    return x * x

st.write(slow_fn(10))
```

---

✨ **Tip:** Run your app with `streamlit run your_script.py` in the terminal.

---

## 📝 Practice Questions

1. Create a Streamlit app that takes two numbers as input and shows their sum.
2. Build a dashboard that displays a bar chart of random numbers.
3. Make an app that lets users upload an image and displays it.
4. Use columns to create a two-panel layout: one for input, one for output.
5. Add a slider to control how many rows of a DataFrame are shown.
