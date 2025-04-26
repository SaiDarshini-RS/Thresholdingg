# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

Developed by : Sai Darshini R S

Register number : 212223230178

### Step 1
Load the necessary packages.
 

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

```python
# Load the necessary packages

import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image=cv2.imread('beach.jpg')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Original image

plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image,cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

# Use Global thresholding to segment the image

_,global_thresholded = cv2.threshold(gray_img, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 

_,otsu_thresholded = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()


```
## Output

### Original Image
![image](https://github.com/user-attachments/assets/43736195-dab6-4fca-b282-c09359b0973f)


### Global Thresholding
![image](https://github.com/user-attachments/assets/a274d862-f99c-4851-a28e-370b43c7a11b)


### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/b4b2a9c8-a314-4920-b7f0-40a720bceac2)


### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/2f5e162a-9d80-4026-b4c7-5f119dc227af)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
