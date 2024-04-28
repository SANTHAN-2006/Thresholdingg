## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program :

### Developed By : K SANTHAN KUMAR
### Register Number : 212223240065

## Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```python
image = cv2.imread('dog.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('dog.jpg',0)
```

# Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image

```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```


# Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

# Display the results
```python
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
## Output :
![image](https://github.com/SANTHAN-2006/Thresholdingg/assets/80164014/8d91ed70-489a-473c-96b8-0b98adbf243a)
<br>
<br>
![image](https://github.com/SANTHAN-2006/Thresholdingg/assets/80164014/e5eb59e8-026e-4b80-9062-1adc98a94889)
<br>
<br>
![image](https://github.com/SANTHAN-2006/Thresholdingg/assets/80164014/45220111-a969-42d0-8da4-dd2f7aa35949)
<br>
<br>
![image](https://github.com/SANTHAN-2006/Thresholdingg/assets/80164014/5502aa4f-f0df-4d18-a0b1-a98ce4874d11)
<br>
<br>
![image](https://github.com/SANTHAN-2006/Thresholdingg/assets/80164014/12d0942f-570d-455f-9200-05c10cbde895)
<br>
<br>
![image](https://github.com/SANTHAN-2006/Thresholdingg/assets/80164014/24288f6c-0b07-4086-b015-bbcf54e0a3b8)
<br>
<br>
![image](https://github.com/SANTHAN-2006/Thresholdingg/assets/80164014/4b63afe6-e4d5-40c3-8ead-e7ca188082ec)
<br>
<br>
![image](https://github.com/SANTHAN-2006/Thresholdingg/assets/80164014/09ec1a1a-6fc3-474b-bd72-d8b462301321)
<br>
<br>
![image](https://github.com/SANTHAN-2006/Thresholdingg/assets/80164014/9afc4909-0446-40f9-92e6-d2e69e627b90)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
