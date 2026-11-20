#  Lane Detection

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections



---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

---
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('sam11.png')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

edges = cv2.Canny(gray_image, 50, 150)

plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line.reshape(-1)
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```
---

##  Expected Output

* Original image
<img width="297" height="410" alt="c230b7c6-3dd2-4079-a32c-906cc82c77fa" src="https://github.com/user-attachments/assets/85b8bd95-5235-4c4c-add9-5f924bb6221f" /><br>

* Grayscale image
<img width="297" height="410" alt="173a3a47-306f-441b-93ad-28a70f5eb76b" src="https://github.com/user-attachments/assets/d5c6bdc9-9c44-4d05-8b6e-d154addd2fae" /><br>

* Thresholded image
* ROI masked image
* Edge detected image
<img width="297" height="410" alt="1970ba90-5ba3-41a9-b1f7-2299251381e9" src="https://github.com/user-attachments/assets/6dba4743-4d25-40d6-8490-29bc1fd2d9bc" /><br>

* Smoothed image
* Detected lines
* Final lane detection output
<img width="297" height="410" alt="ba11aa91-95a2-418b-94a4-bb5b5e5aa882" src="https://github.com/user-attachments/assets/04ed772e-be1c-4e04-8300-7edfc8aa1890" /><br>


---

## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

