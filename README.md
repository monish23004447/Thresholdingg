# THRESHOLDING
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

## Program
## Developed by: AHALYA S
## Register number: 212223230006

```python
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2



# Read the Image and convert to grayscale

image = cv2.imread("C:\\Users\\admin\\Downloads\\river.jpeg")
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("C:\\Users\\admin\\Downloads\\river.jpeg",0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)



# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)


# Display the results

titles=["Gray","Binary","Binary Inv","To Zero","To Zero Inv","Truncate","Otsu","Adaptive Mean","Adaptive Gaussian"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]

plt.figure(figsize=(12,12))
plt.subplot(3,4,1)
plt.imshow(image)
plt.title("Original")
plt.axis("off")

for i in range(9):
    plt.subplot(3,4,i+2)
    plt.imshow(images[i], cmap='gray')
    plt.title(titles[i])
    plt.axis("off")

plt.show()





```
## Output

### Original Image
<img width="1086" height="361" alt="image" src="https://github.com/user-attachments/assets/e7fbe267-8046-47bd-81f5-030061766d85" />


### Global Thresholding
<img width="1102" height="369" alt="image" src="https://github.com/user-attachments/assets/4f8a99a1-a186-4bb4-90ff-92dc474e031d" />

<img width="1036" height="362" alt="image" src="https://github.com/user-attachments/assets/20ac330b-9941-4374-a72a-91701bc0e949" />

<img width="1044" height="363" alt="image" src="https://github.com/user-attachments/assets/2c363dce-10f8-45c5-b21a-b98e92e80d4a" />

<img width="1030" height="360" alt="image" src="https://github.com/user-attachments/assets/b4aa1ecc-7281-4db7-afb2-c7c8e3b4a573" />

<img width="1079" height="349" alt="image" src="https://github.com/user-attachments/assets/e251ba3c-0c25-4b69-9e9b-b57a07c8bab8" />


### Adaptive Thresholding
<img width="1032" height="350" alt="image" src="https://github.com/user-attachments/assets/d805994a-1eab-4a7f-8758-da24f3eef4cc" />
<img width="1084" height="357" alt="image" src="https://github.com/user-attachments/assets/69f012c6-d140-4847-b5bb-b43c28aba997" />



### Optimum Global Thesholding using Otsu's Method
<img width="1097" height="362" alt="image" src="https://github.com/user-attachments/assets/7696ea6f-ae72-4bbc-9299-e86b2a1f8107" />



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
