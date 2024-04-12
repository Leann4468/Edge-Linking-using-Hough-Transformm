## Ex 07 Edge-Linking-using-Hough-Transformm
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

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
### Program:
```python
DEVELOPED BY: LEANN JOBY MATHEW
REG NO: 212222230180
```
#### Read image and convert it to grayscale image
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("car.png",0)
img_c=cv2.imread("car.png",1)
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
```
![image](https://github.com/Leann4468/Edge-Linking-using-Hough-Transformm/assets/121165979/68f82a92-0bd0-4f10-a21f-40f4b9e26018)
            
![image](https://github.com/Leann4468/Edge-Linking-using-Hough-Transformm/assets/121165979/15f843ae-33dd-4015-bc7a-4dd6c9727dc9)

#### Find the edges in the image using canny detector and display
```python
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
![image](https://github.com/Leann4468/Edge-Linking-using-Hough-Transformm/assets/121165979/dc4f7018-f101-479d-bbdc-8eaf6572cc31)

![image](https://github.com/Leann4468/Edge-Linking-using-Hough-Transformm/assets/121165979/6e9dd795-a2ab-4c54-920a-1efc7a94eed6)

#### Detect points that form a line using HoughLinesP
```python
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
![image](https://github.com/Yogeshvar005/Edge-Linking-using-Hough-Transformm/assets/113497367/a1dbac4e-4f78-4923-8775-64c4603b4f2c)

#### Draw lines on the image
```python
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
![image](https://github.com/Yogeshvar005/Edge-Linking-using-Hough-Transformm/assets/113497367/7e793453-130d-4ba1-a03b-230a25dd4b5c)

#### Display the result
```python
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
![image](https://github.com/Yogeshvar005/Edge-Linking-using-Hough-Transformm/assets/113497367/451bdf4f-7158-406b-ab6c-42a2ccce063a)  

![image](https://github.com/Leann4468/Edge-Linking-using-Hough-Transformm/assets/121165979/aca1005e-da64-4f78-8fac-b24771012c30)


### Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
