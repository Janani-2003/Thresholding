# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
<br>
### Step2:
Read the Image and convert to grayscale.
<br>
### Step3:
Use Global thresholding to segment the image.
<br>
### Step4:
Use Adaptive thresholding to segment the image.
<br>
### Step5:
Use Otsu's method to segment the image.

## Program

```python
### Register number : 212221230039 
### Name : JANANI R
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("moana.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("moana.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,130,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,10,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU) 

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
![moanagray](https://github.com/Janani-2003/Thresholding/assets/94288340/b93c849a-83e6-40af-bf86-437cd0a1877d)
<br>
### Global Thresholding
![moanabin](https://github.com/Janani-2003/Thresholding/assets/94288340/a8bdbee9-b537-43ed-82cd-adc57a3785e7)
![moanaInvbin](https://github.com/Janani-2003/Thresholding/assets/94288340/d1c1014c-3684-4193-8be0-710fcd30352c)
![moanaTozero](https://github.com/Janani-2003/Thresholding/assets/94288340/2f73ec13-f505-4177-903b-be0a20749005)
![moanaTozeroInv](https://github.com/Janani-2003/Thresholding/assets/94288340/869f309e-e490-44b6-b9ec-0fb7ccc51c7e)
![moanaTruncate](https://github.com/Janani-2003/Thresholding/assets/94288340/98897359-b778-451d-b9a6-41d470bed3b1)
<br>
### Adaptive Thresholding
![moanaMean](https://github.com/Janani-2003/Thresholding/assets/94288340/02b7d35d-67a8-4c08-9da6-bd11975233e9)
![moanaGauss](https://github.com/Janani-2003/Thresholding/assets/94288340/9d188eb8-a270-4aae-9091-d7de74e60600)
<br>
### Optimum Global Thesholding using Otsu's Method
![moanaOtsu](https://github.com/Janani-2003/Thresholding/assets/94288340/9d0e9cd3-aa8e-40de-9a39-a51a5c0ccbe6)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

