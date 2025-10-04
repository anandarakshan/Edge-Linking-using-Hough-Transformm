# Edge-Linking-using-Hough-Transformm
## Name: Ananda Rakshan K V
## Reg.no: 212223230014
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
```
import numpy as np
import cv2
import matplotlib.pyplot as plt

gray = cv2.imread('bu.png', cv2.IMREAD_GRAYSCALE)
img_color = cv2.imread('bu.png', cv2.IMREAD_COLOR)
img_c = cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB)
gray_rgb = cv2.cvtColor(gray, cv2.COLOR_GRAY2RGB)

gray = cv2.GaussianBlur(gray, (3, 3), 0)

plt.figure(figsize=(13, 13))
plt.subplot(1, 2, 1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1, 2, 2)
plt.imshow(gray_rgb, cmap='gray')
plt.title("Gray Image")
plt.axis("off")
plt.show()
canny = cv2.Canny(gray, 120, 150)

plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)

for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)

plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
<img width="1322" height="440" alt="image" src="https://github.com/user-attachments/assets/766d3eeb-aadb-4c29-9153-fd6ec392c4b5" />


### Canny Edge detector output
<img width="724" height="465" alt="image" src="https://github.com/user-attachments/assets/a1ff01bd-2dad-41dc-a0c5-570b9f3c6bcd" />

### Display the result of Hough transform
<img width="702" height="475" alt="image" src="https://github.com/user-attachments/assets/bc2a10a5-d1ca-4de3-9ac9-bb8c2f7fce56" />

## Result:
Thus, the image has been successfully converted.
