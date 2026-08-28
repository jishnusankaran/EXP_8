# Exp.No : 8 (  Record-THRESHOLDING )

# Name : JISHNUPRIYAN S
# Reg.No : 212223240061
# THRESHOLDING
# Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

# Software Required
Anaconda - Python 3.7
OpenCV
# Algorithm
## Step1:
Read the input image and convert it into a grayscale image.

## Step2:
Apply Global Thresholding with a threshold value of 127.
   
## Step3:
Apply Adaptive Thresholding using the Gaussian method.
  
## Step4:
Apply Otsu’s Thresholding to automatically select the optimal threshold.

## Step5:
Display and compare the original, global, adaptive, and Otsu thresholded images.


# Program
```py


import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the image and convert to grayscale
image = cv2.imread('t.jpeg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


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


# Output
## Original Image
<img width="176" height="256" alt="Screenshot 2026-08-28 154526" src="https://github.com/user-attachments/assets/068a99bd-ceab-4590-9384-387fd8691f09" />




## Global Thresholding

<img width="217" height="292" alt="Screenshot 2026-08-28 154541" src="https://github.com/user-attachments/assets/9dbb040e-016d-4fdc-8ae3-a2fa00de2250" />




## Adaptive Thresholding

<img width="262" height="298" alt="Screenshot 2026-08-28 154533" src="https://github.com/user-attachments/assets/eaecf211-0c33-4458-bd7f-074ecbfeac64" />




## Optimum Global Thesholding using Otsu's Method

<img width="183" height="295" alt="Screenshot 2026-08-28 154547" src="https://github.com/user-attachments/assets/adbc192b-eeb3-4144-9c52-ee338aea6017" />




# Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
