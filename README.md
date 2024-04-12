# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the image
<br>

### Step2:
Read the colour image and convert it into grayscale
<br>

### Step3:
Perform edge detection using canny
<br>

### Step4:
Define the kernel size for erosion and dilation
<br>

### Step5:
Display all images
<br>

 
## Program:

``` Python
# Import the necessary packages
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Create the Text using cv2.putText

img_path='pass.jpg'
img=cv2.imread(img_path)
gray_img=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_img, 100, 200)
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)
erosion = cv2.erode(edges, kernel, iterations=1)
dilation = cv2.dilate(edges, kernel, iterations=1)

# Create the structuring element
plt.figure(figsize=(15, 10))

plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2, 3, 2)
plt.imshow(gray_img, cmap='gray')
plt.title('Black and White Image')
plt.axis('on')

plt.subplot(2, 3, 3)
plt.imshow(edges, cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')

# Erode the image
plt.subplot(2, 3, 4)
plt.imshow(erosion, cmap='gray')
plt.title('Erosion')
plt.axis('on')

# Dilate the image

plt.subplot(2, 3, 5)
plt.imshow(dilation, cmap='gray')
plt.title('Dilation')
plt.axis('on')

plt.show()

```
## Output:

### Display the input Image

![image](https://github.com/ShanmathiShanmugam/erosion-dilation/assets/121243595/593489b6-3e6f-4a22-85e2-6016d8e9dcdb)


### Display the Eroded Image
![image](https://github.com/ShanmathiShanmugam/erosion-dilation/assets/121243595/c92c9ab1-2873-4f46-be22-3ec55d5c1f88)



### Display the Dilated Image
![image](https://github.com/ShanmathiShanmugam/erosion-dilation/assets/121243595/c8948bef-a8c3-453d-b7cf-2dd3f0c79186)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
