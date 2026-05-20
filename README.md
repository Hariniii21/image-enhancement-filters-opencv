# Image Smoothing and Sharpening Using OpenCV

## Aim
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:

- Anaconda – Python 3.7  

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

- **Name:HARINI S**   
- **Register No: 212223240048**
## PROGRAM
### 1. Smoothing Filters
i) Using Averaging Filter
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("img0.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```
### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
##  Output

### Smoothing Filters
i) Using Averaging Filter
<img width="787" height="270" alt="image" src="https://github.com/user-attachments/assets/ea67fbea-2d39-4ce6-a4de-52d2c29e2820" />

ii)Using Weighted Averaging Filter
<img width="598" height="216" alt="image" src="https://github.com/user-attachments/assets/32e7dbb4-b314-4a51-a442-b3410a33028c" />

iii)Using Gaussian Filter
<img width="621" height="218" alt="image" src="https://github.com/user-attachments/assets/91a82c42-a5de-44c0-b81e-235c03b90cfe" />

iv) Using Median Filter
<img width="772" height="281" alt="image" src="https://github.com/user-attachments/assets/19bbd56b-fb39-4744-8908-5a77c9fc5e5a" />

###  Sharpening Filters

i) Using Laplacian Kernal
<img width="613" height="238" alt="image" src="https://github.com/user-attachments/assets/b525626a-7afc-458c-a379-1074a7838808" />

ii) Using Laplacian Operator
<img width="636" height="221" alt="image" src="https://github.com/user-attachments/assets/7c3ae765-42a2-45cb-ae71-92674fdfd578" />


##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.
