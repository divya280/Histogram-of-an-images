# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```
### Developed By:DIVYASHREE V
### Register Number: 212223230051
import matplotlib.pyplot as plt
import cv2
from google.colab import files
import numpy as np

uploaded = files.upload()  

grayscale_image = cv2.imread("panda.webp", cv2.IMREAD_GRAYSCALE)
color_img = cv2.imread("panda.webp")

gray_hist = cv2.calcHist([grayscale_image], [0], None, [256], [0, 256])
hist_b = cv2.calcHist([color_img], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_img], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_img], [2], None, [256], [0, 256])

plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.imshow(grayscale_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(color_img, cv2.COLOR_BGR2RGB))
plt.title('Color Image')
plt.axis('off')
plt.show()

plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.plot(gray_hist, color='black')
plt.title("Grayscale Image Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")

plt.subplot(1, 2, 2)
plt.plot(hist_r, color='red')
plt.plot(hist_g, color='green')
plt.plot(hist_b, color='blue')
plt.title("Color Image Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Pixel Count")
plt.show()

equalized_grey_img = cv2.equalizeHist(grayscale_image)
plt.figure(figsize=(6,4))
plt.title("Equalized Histogram of Gray Image")
plt.hist(equalized_grey_img.ravel(), bins=256, color='black', alpha=0.6)
plt.show()




```
## Output:
### Input Grayscale Image and Color Image
<img width="995" height="402" alt="image" src="https://github.com/user-attachments/assets/6155a45d-95cd-43e4-add2-cce9acdda0a7" />



### Histogram of Grayscale Image and any channel of Color Image

<img width="1031" height="470" alt="image" src="https://github.com/user-attachments/assets/c08503fc-e830-467b-994e-c9522b3ad78b" />


### Histogram Equalization of Grayscale Image.
<img width="547" height="374" alt="image" src="https://github.com/user-attachments/assets/58e5bb31-bfed-4a27-bc67-f47ea0c744d6" />




## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
