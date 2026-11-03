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
Read the image `parrot.jpg` in grayscale format.

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
**Name:SACHIN M**   

### Register No: 212223040177

```

import cv2
from matplotlib import pyplot as plt

image = cv2.imread(r"/content/IMG_8281.JPG.jpeg")

if image is None:
    print("Error: Image not found or path is incorrect.")
else:
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

    plt.figure(figsize=(6, 6))
    plt.imshow(gray_image, cmap='gray')
    plt.title('Original Grayscale Image')
    plt.axis('off')
    plt.show()

hist_original = cv2.calcHist([gray_image], [0], None, [256], [0, 256])

plt.figure(figsize=(6, 4))
plt.plot(hist_original, color='black')
plt.title('Original Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.xlim([0, 256])
plt.grid(True)
plt.show()

equalized_image = cv2.equalizeHist(gray_image)

plt.figure(figsize=(6, 6))
plt.imshow(equalized_image, cmap='gray') 
plt.title('Equalized Image')
plt.axis('off')
plt.show()

hist_equalized = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])

plt.figure(figsize=(6, 4))
plt.plot(hist_equalized, color='black')
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.xlim([0, 256])
plt.grid(True)
plt.show()

```

---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed

  
  <img width="688" height="397" alt="image" src="https://github.com/user-attachments/assets/9dec16ef-b879-47e6-ab3c-a3d382054e31" />

- Histogram of original grayscale image is plotted

  
  <img width="885" height="488" alt="image" src="https://github.com/user-attachments/assets/0359dc28-48e1-48bb-94fb-4fdc826ffdae" />

- Enhanced image after histogram equalization is displayed

  
  <img width="722" height="382" alt="image" src="https://github.com/user-attachments/assets/f51ab819-2756-4ed0-8dd1-2ac60f4cbb68" />

- Histogram of enhanced grayscale image shows improved contrast

  
  <img width="808" height="523" alt="image" src="https://github.com/user-attachments/assets/7cf17bb5-d3c3-489c-85e9-cd0e34b29b28" />



---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
