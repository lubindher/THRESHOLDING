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
### Step 6:
Display the results.
<br>

## Program
```
DEVELOPED BY : Lubindher S
REG NO : 212222240056
```


# Load the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```





# Read the Image and convert to grayscale
```
image=cv2.imread("dipt.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("dipt.jpg",0)
```




# Use Global thresholding to segment the image
```
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```




# Use Adaptive thresholding to segment the image
```
ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```




# Use Otsu's method to segment the image 
```
thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```




# Display the results
```
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




## Output

### Original Image

![download](https://github.com/aldrinlijo04/THRESHOLDING/assets/118544279/0291decd-bb53-442c-8299-52ca3520f290)

<br>

### Global Thresholding
![download](https://github.com/aldrinlijo04/THRESHOLDING/assets/118544279/811b2916-24a3-4f83-8480-95bdf6e26eb7)

![download](https://github.com/aldrinlijo04/THRESHOLDING/assets/118544279/f9788a58-09f8-4f98-b0be-61af49320eec)

![download](https://github.com/aldrinlijo04/THRESHOLDING/assets/118544279/601fd421-8de7-41b5-8db4-53cf9cf751ae)

![download](https://github.com/aldrinlijo04/THRESHOLDING/assets/118544279/21da855f-ac67-4e6a-87ed-622ef3eaf900)

![download](https://github.com/aldrinlijo04/THRESHOLDING/assets/118544279/a0987493-1e10-47e0-ad95-948698d1d9a0)

<br>

### Adaptive Thresholding

![download](https://github.com/aldrinlijo04/THRESHOLDING/assets/118544279/5799038a-bf66-48c8-a7fb-065fa070fec4)

![download](https://github.com/aldrinlijo04/THRESHOLDING/assets/118544279/9e9e898b-97b7-4ddb-92e1-92a5dc3690ab)

<br>

### Optimum Global Thesholding using Otsu's Method

![download](https://github.com/aldrinlijo04/THRESHOLDING/assets/118544279/3201fdc0-a268-427a-b246-9378cbb0d707)


<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
