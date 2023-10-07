# THRESHOLDING
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
<br>

### Step6:
Display the results.
<br>

## Program
```
Developed by:Kavinesh M
Register number :212222230064
```
# Load the necessary packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```




# Read the Image and convert to grayscale
```python
image=cv2.imread("d.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("d.jpg",0)
```



# Use Global thresholding to segment the image
```python
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image
```python
ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Use Otsu's method to segment the image 
```python
thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```



# Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
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




```
## Output

### Original Image
<br>

![image](https://github.com/kavinesh8476/THRESHOLDING/assets/118466561/f6a51b8f-ad37-459e-9085-73338f6574ad)

<br>


### Global Thresholding
<br>

![image](https://github.com/kavinesh8476/THRESHOLDING/assets/118466561/aa0e3419-8184-4d05-830e-1c341431e192)
![image](https://github.com/kavinesh8476/THRESHOLDING/assets/118466561/c31cb981-acab-4dd5-8cfc-1d0460e3b7e5)

<br>


### Adaptive Thresholding
<br>

![image](https://github.com/kavinesh8476/THRESHOLDING/assets/118466561/6f9dd0a8-088c-4cad-bfd7-a64d1cb76dc1)

<br>


### Optimum Global Thesholding using Otsu's Method
<br>

![image](https://github.com/kavinesh8476/THRESHOLDING/assets/118466561/4ac9c7f6-addd-4d54-bc65-843fa455b4b3)

<br>



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

