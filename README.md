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

# Program 
## Developed By: Deepika S
## Reg NO: 212223230039

```
import cv2
import matplotlib.pyplot as plt
image = cv2.imread("C:/Users/admin/Downloads/Bird.jpg")  # Replace with your image path
# Display Input Image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Input Image')
plt.axis('off')
plt.show()
```
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display Grayscale Image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
plt.show()
```
```
edges = cv2.Canny(gray_image, 50, 150, apertureSize=3)
# Display Canny Edge Detection Output   
plt.imshow(edges, cmap='gray')
plt.title('Canny Edge Detector Output')
plt.axis('off')
plt.show()
```
```
import numpy as np
# Detect lines using the probabilistic Hough transform
lines = cv2.HoughLinesP(edges, rho=1, theta=np.pi/180, threshold=100, minLineLength=50, maxLineGap=10)

# Draw the lines on the original image
output_image = image.copy()

if lines is not None:
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(output_image, (x1, y1), (x2, y2), (0, 255, 0), 2)
# Display Hough Transform Result
plt.imshow(cv2.cvtColor(output_image, cv2.COLOR_BGR2RGB))
plt.title('Hough Transform - Line Detection')
plt.axis('off')
plt.show()
```

# Output
![image](https://github.com/user-attachments/assets/eb9579dc-b880-4895-9cfa-8cb832631515)

![image](https://github.com/user-attachments/assets/38e26022-660f-4191-89a0-6389f385e2a8)

![image](https://github.com/user-attachments/assets/08f69abc-37b8-4d41-a1eb-63973f73a1e1)

![image](https://github.com/user-attachments/assets/ce233ac2-2213-4063-a05a-fa0f3e89be41)


# Result
Python program to detect the lines using Hough Transform executed successfully.




