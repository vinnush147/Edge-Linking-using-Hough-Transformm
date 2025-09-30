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
## Program 
Name: Vinnush kumar L S
Reg no.212223230244
### Input image and grayscale image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Tiger.jpg')  # Replace with your image path
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
```
<Figure size 640x480 with 1 Axes><img width="515" height="323" alt="image" src="https://github.com/user-attachments/assets/dad80fe7-5b94-463f-afba-e2acd1ca2c5f" />

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
<Figure size 640x480 with 1 Axes><img width="515" height="323" alt="image" src="https://github.com/user-attachments/assets/34085261-3486-405c-bfe7-df9a6443d285" />


### Canny Edge detector output
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
<Figure size 640x480 with 1 Axes><img width="515" height="323" alt="image" src="https://github.com/user-attachments/assets/8c7c367f-a901-481e-823f-1a8e6070a715" />



### Display the result of Hough transform
```
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')

```
<Figure size 640x480 with 1 Axes><img width="515" height="323" alt="image" src="https://github.com/user-attachments/assets/cf588161-9202-40ec-a78c-61e7f7c418b7" />


### Result:
Thus,The Python program to detect the lines using Hough Transform run successfully.
