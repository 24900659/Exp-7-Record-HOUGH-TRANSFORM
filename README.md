# Exp-7-Record-HOUGH-TRANSFORM

Edge-Linking-using-Hough-Transform

NAME : MOHANA K.V.S.L

REG NO : 212224240093

Aim:

To write a Python program to detect the lines using Hough Transform.

Software Required:

Anaconda - Python 3.7

Algorithm:

Step1:
Import all the necessary modules for the program.

Step2:
Load a image using imread() from cv2 module.

Step3:
Convert the image to grayscale.

Step4:
Using Canny operator from cv2,detect the edges of the image.

Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('pic.jpeg')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')
```
```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
```
edges = cv2.Canny(gray_image, 50, 150)

plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')
```
Output
Input image and grayscale image

<img width="498" height="687" alt="image" src="https://github.com/user-attachments/assets/6e379310-8e11-42b6-94b4-d0aedbd0da67" />

<img width="532" height="676" alt="image" src="https://github.com/user-attachments/assets/43681b86-f36e-451e-a5dd-60121d4d11fa" />

Canny Edge detector output

<img width="522" height="676" alt="image" src="https://github.com/user-attachments/assets/fd93a695-a89e-4616-b3a9-c9198ec48671" />

Display the result of Hough transform

<img width="511" height="677" alt="image" src="https://github.com/user-attachments/assets/79661fb9-415d-4d38-833d-d2ba0d74e31c" />

Result:

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.
