# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
# Step1
Import libraries and read the saved images using cv2.imread().

# Step2
Convert the saved BGR image to RGB using cvtColor().

# Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

# Step4
Apply the filters using cv2.filter2D() for each respective filters.

# Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().

## Program:
### Developed By   : Gayathri A
### Register Number: 212221230028
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("gg.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
```

### 1. Smoothing Filters :

i) Using Averaging Filter
```Python
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")
```
ii) Using Weighted Averaging Filter
```Python
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")
```
iii) Using Gaussian Filter
```Python
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")
```

iv) Using Median Filter
```Python
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")
```

### 2. Sharpening Filters :

i) Using Laplacian Kernal
```Python
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")
```

ii) Using Laplacian Operator
```Python
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")
```

## OUTPUT:
### 1. Smoothing Filters


i) Using Averaging Filter

![6 1](https://user-images.githubusercontent.com/94154854/232313450-3754b73f-e750-434b-ae5b-a1506911dba3.png)


ii) Using Weighted Averaging Filter

![6 2](https://user-images.githubusercontent.com/94154854/232313455-1426cb1f-011d-4173-9a21-b214f46492fb.png)


iii) Using Gaussian Filter

![6 3](https://user-images.githubusercontent.com/94154854/232313472-3adaa275-c266-4371-ab5d-3f745c2334ed.png)


iv) Using Median Filter

![6 4](https://user-images.githubusercontent.com/94154854/232313482-c779eb2f-720a-46f7-90d1-c7e7d8cf99d4.png)


### 2. Sharpening Filters


i) Using Laplacian Kernal

![6 5](https://user-images.githubusercontent.com/94154854/232313489-f0425580-0c50-472e-9c75-6f7ccd747e4a.png)


ii) Using Laplacian Operator

![6 6](https://user-images.githubusercontent.com/94154854/232313499-c569f3c6-505c-4f49-935f-92b3e1008f61.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
