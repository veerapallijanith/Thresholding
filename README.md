# Thresholding
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## Program

```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("hinata.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("hinata.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()


```
## Output

### Original Image

![tj2](https://user-images.githubusercontent.com/75234814/169644081-d88036db-7b9d-4b37-93ef-8eca4d31500d.jpg)



### Global Thresholding
![tj3](https://user-images.githubusercontent.com/75234814/169644083-b87ac6f2-3789-4705-b7c8-bfc0ad756bad.jpg)



### Adaptive Thresholding
![tj4](https://user-images.githubusercontent.com/75234814/169644084-a88c4606-072f-4d8b-ab78-2d01de082de8.jpg)



### Optimum Global Thesholding using Otsu's Method
![tj5](https://user-images.githubusercontent.com/75234814/169644087-e2a917bf-0ecb-4022-bc68-2bcb232a4cb7.jpg)




## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
