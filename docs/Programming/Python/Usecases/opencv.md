# OpenCV 🖼️

OpenCV (Open Source Computer Vision Library) is a powerful library for computer vision and image processing tasks. It provides tools for image manipulation, object detection, video analysis, and more.

---

## Key Use Cases 🚀

### 1. Image Processing 🖌️
Perform operations like resizing, cropping, filtering, and color transformations.

**Example:**
```python
import cv2

# Load an image
image = cv2.imread('example.jpg')

# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Save the processed image
cv2.imwrite('gray_example.jpg', gray_image)
```

---

### 2. Object Detection 🔍
Detect objects like faces, eyes, or custom objects using pre-trained models.

**Example:**
```python
import cv2

# Load pre-trained Haar Cascade for face detection
face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')

# Read an image
image = cv2.imread('example.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Detect faces
faces = face_cascade.detectMultiScale(gray_image, scaleFactor=1.1, minNeighbors=5)

# Draw rectangles around detected faces
for (x, y, w, h) in faces:
    cv2.rectangle(image, (x, y), (x+w, y+h), (255, 0, 0), 2)

cv2.imwrite('faces_detected.jpg', image)
```

---

### 3. Video Analysis 🎥
Process video streams for tasks like motion detection or frame extraction.

**Example:**
```python
import cv2

# Open video file
video = cv2.VideoCapture('example.mp4')

while True:
    ret, frame = video.read()
    if not ret:
        break

    # Convert frame to grayscale
    gray_frame = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)

    # Display the frame
    cv2.imshow('Video Frame', gray_frame)

    # Exit on pressing 'q'
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

video.release()
cv2.destroyAllWindows()
```

---

### 4. Image Segmentation ✂️
Segment images into regions based on color or intensity.

**Example:**
```python
import cv2
import numpy as np

# Load an image
image = cv2.imread('example.jpg')

# Apply thresholding
_, segmented_image = cv2.threshold(cv2.cvtColor(image, cv2.COLOR_BGR2GRAY), 127, 255, cv2.THRESH_BINARY)

cv2.imwrite('segmented_example.jpg', segmented_image)
```

---

### 5. Feature Detection and Matching 🧩
Detect and match features between images for tasks like stitching or object recognition.

**Example:**
```python
import cv2

# Load two images
image1 = cv2.imread('image1.jpg', cv2.IMREAD_GRAYSCALE)
image2 = cv2.imread('image2.jpg', cv2.IMREAD_GRAYSCALE)

# Initialize ORB detector
orb = cv2.ORB_create()

# Detect and compute features
keypoints1, descriptors1 = orb.detectAndCompute(image1, None)
keypoints2, descriptors2 = orb.detectAndCompute(image2, None)

# Match features using BFMatcher
bf = cv2.BFMatcher(cv2.NORM_HAMMING, crossCheck=True)
matches = bf.match(descriptors1, descriptors2)

# Draw matches
matched_image = cv2.drawMatches(image1, keypoints1, image2, keypoints2, matches, None)

cv2.imwrite('matched_example.jpg', matched_image)
```

---

## Practice Questions 📝

1. Write a program to detect edges in an image using OpenCV.
2. Create a script to capture video from your webcam and save it to a file.
3. Implement a program to detect circles in an image using the Hough Circle Transform.
4. Use OpenCV to blend two images together.
5. Write a program to track an object in a video based on its color.
