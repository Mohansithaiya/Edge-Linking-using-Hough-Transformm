# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:

### Developed by : MOHAN S
### Register no : 212223240094
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('EAGLE.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```
## Output

![Screenshot 2025-04-29 140628](https://github.com/user-attachments/assets/6418ca7b-e075-43c9-a91f-ba9a4620bae6)


## Grayscale Image:
```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
plt.subplot(2, 2, 2)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
## Output

![Screenshot 2025-04-29 140636](https://github.com/user-attachments/assets/ac9e4773-4ca8-4db2-b2a5-d2d99676df8a)


## Canny Edge Detector:
```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
plt.subplot(2, 2, 3)
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
```
## Output

![Screenshot 2025-04-29 140642](https://github.com/user-attachments/assets/200242ac-25fa-4ceb-a3e9-a45dc56e3f2d)


## Detect lines using the probabilistic Hough transform
```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
        plt.subplot(2, 2, 4)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
```
## Output

![Screenshot 2025-04-29 140648](https://github.com/user-attachments/assets/e5d5cd29-5bba-4bfe-b2a8-c7c8f7e53c71)


# Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
