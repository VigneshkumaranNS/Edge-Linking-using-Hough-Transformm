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
```PYTHON
NAME: VIGNESH KUMARAN N S
REG: 212222230171
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("butterfly.jpg",0)
img_c=cv2.imread("butterfly.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()

canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()

lines=cv2.HoughLinesP(canny,1,np.pi/180,
                threshold=80,minLineLength=50,maxLineGap=250)

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
<img src = "https://github.com/Adhithyaram29D/Edge-Linking-using-Hough-Transformm/assets/119393540/58f5c317-13c2-4654-817c-c1d435a88968" width= "600">

### Canny Edge detector output
<img src = "https://github.com/Adhithyaram29D/Edge-Linking-using-Hough-Transformm/assets/119393540/53d78387-0929-42f5-93fc-4324154b9126" width="350">

### Display the result of Hough transform
<img src ="https://github.com/Adhithyaram29D/Edge-Linking-using-Hough-Transformm/assets/119393540/1ee0de47-b785-416d-8607-f13bd871e448" width="350">

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
