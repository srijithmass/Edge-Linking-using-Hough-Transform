# Edge-Linking-using-Hough-Transform

## Aim:

To write a Python program to detect the lines using Hough Transform.

## Software Required:

Anaconda - Python 3.7

## Algorithm:

### Step1:

Import all the necessary Python libraries which are required for the program.

### Step2:

Load a image using imread() from cv2 module.

### Step3:

Convert the image to grayscale.

### Step4:

Using Canny operator from cv2,detect the edges of the image

### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:

```Python
import cv2
import matplotlib.pyplot as plt

image=cv2.imread('edge.png',1)
#image=cv2.resize(image,(1200,800))

cv2.imshow(' ',image)
import numpy as np
edges1 = cv2.Canny(image,100,150)

lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=100, minLineLength=20,maxLineGap=50)


for line in lines:
    x1, y1, x2, y2 = line [0]
    cv2.line(image,(x1, y1),(x2, y2),(203, 48, 255),1)


cv2.imshow('gray',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## Output

![](op.png)
![](op1.png)

## Result:

Thus the program is written with python and OpenCV to detect lines using Hough transform.