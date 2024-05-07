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

## PROGRAM:
```
DEVELOPED BY:PREETHA.S
REGISTER NO:212222230110
```
## READ IMAGE AND CONVERT IT INTO GRAYSCALE IMAGE:
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("leaf.jpeg",0)
img_c=cv2.imread("leaf.jpeg",1)
img=cv2.resize(img,(200,200))
img_c=cv2.resize(img_c,(200,200))
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```

## FIND THE EDGES IN THE IMAGE USING CANNY EDGE DETECTOR AND DISPLAY:
```
canny=cv2.Canny(img_c,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```

## DETECT POINTS THAT FORM A LINE USING HOUGHLINESP
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```

## DRAW LINES ON THE IMAGE:
```
for line in lines:
  x1,y1,x2,y2=line[0]
  cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```

## DISPLAY THE RESULT:
```
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()

```


## Output

### Input image and grayscale image

![image](https://github.com/Preetha-Senthamilan/Edge-Linking-using-Hough-Transformm/assets/119390282/432fb33c-cd85-4d2d-81c0-a31c7bd248be)


### Canny Edge detector output

![image](https://github.com/Preetha-Senthamilan/Edge-Linking-using-Hough-Transformm/assets/119390282/77084409-7d82-4b81-823f-f4164e29461a)

### Display the result image

![image](https://github.com/Preetha-Senthamilan/Edge-Linking-using-Hough-Transformm/assets/119390282/1147f7c1-23be-4ca5-b9bd-50f3a4611a25)

## RESULT:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
