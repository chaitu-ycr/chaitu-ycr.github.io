# 🖼️ Pillow: Python Imaging Library

**Pillow** is a user-friendly Python library for working with images. It lets you easily open, edit, and save images in many formats. Pillow is a modern fork of the original PIL library and works with Python 3.

---

## 🚀 Installation

```bash
pip install Pillow
```

---

## ⚡ Common Use Cases

Below are the most common things you can do with Pillow, each with a simple example.

### 📂 1. Open an Image

```python
from PIL import Image

img = Image.open('example.jpg')
img.show()
```

---

### 📏 2. Resize an Image

```python
from PIL import Image

img = Image.open('example.jpg')
resized = img.resize((400, 300))
resized.show()
```

---

### ✂️ 3. Crop an Image

```python
from PIL import Image

img = Image.open('example.jpg')
cropped = img.crop((50, 50, 200, 200))  # (left, top, right, bottom)
cropped.show()
```

---

### 💾 4. Save an Image (Different Format)

```python
from PIL import Image

img = Image.open('example.jpg')
img.save('example.png')
```

---

### 📝 5. Add Text to an Image

```python
from PIL import Image, ImageDraw, ImageFont

img = Image.open('example.jpg')
draw = ImageDraw.Draw(img)
font = ImageFont.load_default()
draw.text((10, 10), "Hello, Pillow!", font=font, fill="white")
img.save('example_with_text.jpg')
```

---

### 🔄 6. Rotate or Flip an Image

```python
from PIL import Image

img = Image.open('example.jpg')
rotated = img.rotate(90)  # Rotate 90 degrees
rotated.show()

flipped = img.transpose(Image.FLIP_LEFT_RIGHT)  # Flip horizontally
flipped.show()
```

---

### 🎨 7. Convert to Grayscale

```python
from PIL import Image

img = Image.open('example.jpg')
gray = img.convert('L')
gray.show()
```

---

## 📚 Summary

Pillow makes image processing in Python simple and fun! You can open, edit, and save images with just a few lines of code. For more, check the [Pillow documentation](https://pillow.readthedocs.io/en/stable/).

---

## 📝 Practice Questions

1. Open an image and resize it to 100x100 pixels.
2. Crop the center 50x50 region from an image.
3. Add your name as text to the bottom-right corner of an image.
4. Convert an image to grayscale and save it as a new file.
5. Rotate an image by 180 degrees and display it.
