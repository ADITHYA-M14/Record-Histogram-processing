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
Read the image `Qno. 1.jpg` in grayscale format.

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
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read grayscale image
img = cv2.imread('Qno. 1.png', cv2.IMREAD_GRAYSCALE)

if img is None:
    print("Image not found. Please upload Qno. 1.png")
else:
    plt.imshow(img, cmap='gray')
    plt.title('Original Grayscale Image')
    plt.axis('off')
    plt.show()
plt.hist(img.ravel(), 256, range=[0, 256], color='black')
plt.title('Original Image Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()
img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range=[0, 256], color='blue')
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()
plt.imshow(img_eq, cmap='gray')
plt.title('Histogram Equalized Grayscale Image')
plt.axis('off')
plt.show()
# Read original color image
img_color = cv2.imread('Qno. 1.png', cv2.IMREAD_COLOR)

# Convert BGR to HSV
img_hsv = cv2.cvtColor(img_color, cv2.COLOR_BGR2HSV)

# Apply histogram equalization to V channel
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert HSV back to BGR
img_eq_color = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Convert BGR to RGB for displaying
original_rgb = cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB)
equalized_rgb = cv2.cvtColor(img_eq_color, cv2.COLOR_BGR2RGB)

# Display images
plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(original_rgb)
plt.title('Original Color Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(equalized_rgb)
plt.title('Equalized Color Image')
plt.axis('off')

plt.show()
plt.figure(figsize=(12, 10))

# Original color image
plt.subplot(2, 2, 1)
plt.imshow(original_rgb)
plt.title('Original Color Image')
plt.axis('off')

# Equalized color image
plt.subplot(2, 2, 2)
plt.imshow(equalized_rgb)
plt.title('Equalized Color Image')
plt.axis('off')

# Original histogram
plt.subplot(2, 2, 3)
plt.hist(img_color.ravel(), 256, range=[0, 256], color='black')
plt.title('Original Image Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

# Equalized histogram
plt.subplot(2, 2, 4)
plt.hist(img_eq_color.ravel(), 256, range=[0, 256], color='blue')
plt.title('Equalized Image Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

plt.tight_layout()
plt.show()
```

### Developed By:
**Name:** ADITHYA M

### Register No: 212224230008

---

##  Output
<img width="552" height="343" alt="image" src="https://github.com/user-attachments/assets/d069a70d-b986-4989-a417-d721c118d116" />


<img width="570" height="434" alt="image" src="https://github.com/user-attachments/assets/cbf0d0c5-8c97-4eaf-a12e-62c78057e083" />


<img width="570" height="434" alt="image" src="https://github.com/user-attachments/assets/bbc4c8c9-a244-45d4-81df-cc3cac7b3729" />


<img width="552" height="343" alt="image" src="https://github.com/user-attachments/assets/02f8dfb2-1553-4cdd-8f12-66360889352d" />


<img width="552" height="343" alt="image" src="https://github.com/user-attachments/assets/8ecbad52-f3cf-45cf-90fe-db6d7602498c" />


<img width="570" height="434" alt="image" src="https://github.com/user-attachments/assets/a8b7b4a8-de8d-4dc1-bb56-228aece9adfc" />


<img width="1524" height="414" alt="image" src="https://github.com/user-attachments/assets/401e0593-de3a-495c-aa5f-2c0eb602255f" />


<img width="1237" height="372" alt="image" src="https://github.com/user-attachments/assets/bdf95727-edbc-476f-8fd2-7f1ed95574fe" />






### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
