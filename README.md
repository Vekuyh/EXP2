# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program
```
import cv2

# Open webcam
cap = cv2.VideoCapture(0)

# Capture one frame
ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_image.jpg", frame)
    print("Captured image is saved as captured_image.jpg")
else:
    print("Failed to capture image")

cap.release()
cv2.destroyAllWindows()


import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    if not ret:
        break

    cv2.imshow("Live Webcam", frame)

    # Press 'q' to quit
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()

import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    if not ret:
        break

    # Resize the frame
    resized = cv2.resize(frame, (640, 480))

    cv2.imshow("Resized Video (640x480)", resized)

    # Press 'q' to quit
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()


import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()

    if not ret:
        break

    # Rotate 90 degrees clockwise
    rotated = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    cv2.imshow("Rotated Video", rotated)

    # Press 'q' to quit
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```
### Developed By:
**Name:** VENKATESH.P

### Register No:
212225230295  

---

## Output
![alt text](<Screenshot 2026-11-22 125816.png>)
![alt text](<Screenshot 2026-11-22 125851.png>)
![alt text](<Screenshot 2026-11-22 125903.png>)
---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.