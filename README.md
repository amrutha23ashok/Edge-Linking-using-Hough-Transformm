# Edge-Linking-using-Hough-Transformm
### Aim:
To write a Python program to detect the lines using Hough Transform.

### Software Required:
Anaconda - Python 3.7

### Algorithm:
#### Step1:
Import all the necessary modules for the program.

#### Step2:
Load a image using imread() from cv2 module.

#### Step3:
Convert the image to grayscale.

#### Step4:
Using Canny operator from cv2,detect the edges of the image.

#### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

### program:
```
Developed by: amrutha
REGISTER NUMBER: 212222110004
```
Read image and convert it to grayscale image
```
import cv2
import numpy as np
r=cv2.imread('dipt_img.jpg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('original',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
Find the edges in the image using canny detector and display
```
canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

Detect points that form a line using HoughLinesP
```
lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,maxLineGap = 7)

```

Draw lines on the image
```
for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)
```


Display the result
```
cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Output

#### Input image and grayscale image
![image](https://github.com/user-attachments/assets/caabbeca-971e-466e-b10e-df86f8d5d581)
![image](https://github.com/user-attachments/assets/ef622d9f-64fc-438c-a1ca-9e38ff373a15)


#### Canny Edge detector output
![image](https://github.com/user-attachments/assets/ac239b54-f02e-407a-913c-4ba306a0d6eb)


#### Display the result of Hough transform
![image](https://github.com/user-attachments/assets/8ff2259e-93e7-4d7a-a399-1b9c51c5c299)

### Result:
Thus, To write a Python program to detect the lines using Hough Transform is executed successfully.

