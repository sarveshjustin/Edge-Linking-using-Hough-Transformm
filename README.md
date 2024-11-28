```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Qn_7_.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Input Image")
plt.axis('off')
(-0.5, 267.5, 187.5, -0.5)
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
(-0.5, 267.5, 187.5, -0.5)
edges = cv2.Canny(gray_image, 50, 150) 
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
(-0.5, 267.5, 187.5, -0.5)
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0] 
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2) 
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Result of Hough Transform")
plt.axis('off')
```
