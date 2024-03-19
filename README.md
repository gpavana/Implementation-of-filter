# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import necessary libraries: OpenCV, NumPy, and Matplotlib.Read an image, convert it to RGB format, define an 11x11 averaging kernel, and apply 2D convolution filtering.Display the original and filtered images side by side using Matplotlib.
### Step2
Define a weighted averaging kernel (kernel2) and apply 2D convolution filtering to the RGB image (image2).Display the resulting filtered image (image4) titled 'Weighted Averaging Filtered' using Matplotlib's imshow function.
### Step3
Apply Gaussian blur with a kernel size of 11x11 and standard deviation of 0 to the RGB image (image2).Display the resulting Gaussian-blurred image (gaussian_blur) titled 'Gaussian Blurring Filtered' using Matplotlib's imshow function.
### Step4
Apply median blur with a kernel size of 11x11 to the RGB image (image2).Display the resulting median-blurred image (median) titled 'Median Blurring Filtered' using Matplotlib's imshow function.
### Step5
Define a Laplacian kernel (kernel3) and perform 2D convolution filtering on the RGB image (image2).Display the resulting filtered image (image5) titled 'Laplacian Kernel' using Matplotlib's imshow function.
### Step 6:
Apply the Laplacian operator to the RGB image (image2) using OpenCV's cv2.Laplacian function.Display the resulting image (new_image) titled 'Laplacian Operator' using Matplotlib's imshow function.
## Program:
### Developed By   :PAVANA.G
### Register Number:212222230105
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("bird.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)

plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title('Original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')

```
ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("bird.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

kernel2=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title('WEIGHTED AVERAGE FILTERING')

```
iii) Using Gaussian Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("bird.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

guassian_blur=cv2.GaussianBlur(src=image2,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.imshow(guassian_blur)
plt.title('GAUSSIAN FILTER')

```
iv) Using Median Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("bird.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

median=cv2.medianBlur(src=image2,ksize=11)
plt.imshow(median)
plt.title('MEDIAN FILTER')

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("bird.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
image3=cv2.filter2D(image2,-1,kernel3)

plt.imshow(image3)
plt.title('LAPLACIAN KERNEL')

```
ii) Using Laplacian Operator
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread("bird.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)

new_image=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(new_image)
plt.title('LAPLACIAN OPERATOR')

```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
![image](https://github.com/gpavana/Implementation-of-filter/assets/118787343/ead20c27-783e-47e7-9316-80b9c770811c)

ii) Using Weighted Averaging Filter
![image](https://github.com/gpavana/Implementation-of-filter/assets/118787343/850d5e20-ec80-4fe3-be8b-c0baf878322f)

iii) Using Gaussian Filter
![image](https://github.com/gpavana/Implementation-of-filter/assets/118787343/3c44acc4-5e42-4007-b153-dffac6acac0b)

iv) Using Median Filter
![image](https://github.com/gpavana/Implementation-of-filter/assets/118787343/e7543bfe-66cf-4429-b592-d8457dab89d2)

### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal
![image](https://github.com/gpavana/Implementation-of-filter/assets/118787343/f4b45a88-8788-4551-9356-81374f7ad01f)

ii) Using Laplacian Operator
![image](https://github.com/gpavana/Implementation-of-filter/assets/118787343/32aa4b22-46b6-4578-bb7c-a43ee7957d93)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
