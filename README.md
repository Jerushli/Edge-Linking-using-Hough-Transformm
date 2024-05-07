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
### PROGRAM
```python
import cv2
import numpy as np

r=cv2.imread('rab.jpg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('origianl',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()

canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()

lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)

for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)

cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output
### ORIGINAL IMAGE
![image](https://github.com/Jerushli/Edge-Linking-using-Hough-Transformm/assets/120041243/9bbc671c-bd38-4956-9595-b7b69c639082)

### Input image and grayscale image
![image](https://github.com/Jerushli/Edge-Linking-using-Hough-Transformm/assets/120041243/9924a103-199f-4161-8c8f-0b696904ab92)

### Canny Edge detector output
![image](https://github.com/Jerushli/Edge-Linking-using-Hough-Transformm/assets/120041243/f73af502-a20e-481f-9651-2c1923f55f42)

### Display the result of Hough transform
![image](https://github.com/Jerushli/Edge-Linking-using-Hough-Transformm/assets/120041243/228485cc-5d4a-4b16-96fc-d10ac2fa8a2b)

### RESULT
Thus the program is written with Python and OpenCV to detect lines using Hough transform.
