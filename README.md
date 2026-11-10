# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `ashfak.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
**Name:** ASHFAK N  

### Register No:
212225230022

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

```python

img = cv2.imread('ASHFAK.png', cv2.IMREAD_GRAYSCALE)
```


```python
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```

```python

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```

```python
img_eq = cv2.equalizeHist(img)
```

```python
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```

```python

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

```python

img = cv2.imread('ASHFAK.png', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```

```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```

```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```









---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed

<img width="352" height="434" alt="image" src="https://github.com/user-attachments/assets/8e518f44-d023-4c14-8534-8a0c395c4f53" />



- Histogram of original grayscale image is plotted

<img width="579" height="434" alt="image" src="https://github.com/user-attachments/assets/3d567239-2055-4057-a885-3d8145f32e75" />



- Enhanced image after histogram equalization is displayed

<img width="579" height="434" alt="image" src="https://github.com/user-attachments/assets/7ee66beb-eeea-44f1-ba89-d39da3d08cb4" />



- Histogram of enhanced grayscale image shows improved contrast


<img width="352" height="434" alt="image" src="https://github.com/user-attachments/assets/3c1a005c-e211-44b8-b727-e25ee3cbe3ce" />


### Color Image Histogram Equalization

- Original color image is displayed

<img width="352" height="434" alt="image" src="https://github.com/user-attachments/assets/917a2861-a8cc-4abb-80f5-cb2ab4cfe37e" />


- Histogram of B, G, R channels is plotted

<img width="547" height="434" alt="image" src="https://github.com/user-attachments/assets/e8fbbd73-5534-4b71-8393-3fd242083e00" />


- Enhanced image after HSV-based equalization is displayed

<img width="1182" height="414" alt="image" src="https://github.com/user-attachments/assets/dcd0ade5-f9d4-4b3a-a6bc-ec0d5b8bbbc0" />




- Histogram of enhanced image shows better intensity distribution

<img width="1214" height="372" alt="image" src="https://github.com/user-attachments/assets/18e5da30-f513-4cec-8929-29014edaec81" />




---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
