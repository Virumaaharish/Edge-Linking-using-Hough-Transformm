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
<img width="417" height="400" alt="image" src="https://github.com/user-attachments/assets/6c9a4ce0-f553-4142-b18f-43a49c496123" />

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
<img width="425" height="399" alt="image" src="https://github.com/user-attachments/assets/7a56315d-eb40-4f3f-9e36-0c8d816f6a7b" />


### Canny Edge detector output
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
<img width="424" height="406" alt="image" src="https://github.com/user-attachments/assets/612a26b1-40bf-4602-8d21-01d45b639454" />


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
<img width="430" height="397" alt="image" src="https://github.com/user-attachments/assets/cac6b1d0-b4ee-4e3d-b5c8-4c9ed552c9be" />


### Result:
Thus,The Python program to detect the lines using Hough Transform run successfully.
