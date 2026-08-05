# Geometric Transformations Using OpenCV

---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program

### Developed By:
**Name:** JAYAPRIYA P

### Register No:
212225040144 

Step 1 : Load the image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('baseball.jpg')
```
Step 2 : Display the original image
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off')
```
Step 3 : Image Translation
```
tx, ty = 100, 50  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]]) 
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Translated Image")  
plt.axis('off')
```
Step 4 : Image Shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) 
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) 
plt.title("Sheared Image") 
plt.axis('off')
```
Step 5: Image Reflection
```
reflected_image = cv2.flip(image, 2)  
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")  
plt.axis('off')
```
Step 6: Image Rotation
```
(height, width) = image.shape[:2] 
angle = 45  
center = (width // 2, height // 2)  
M_rotation = cv2.getRotationMatrix2D(center, angle, 1) 
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image") 
plt.axis('off')
```
Step 7: Image Cropping
```
x, y, w, h = 100, 100, 200, 150
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image") 
plt.axis('off')
```

---

##  Output

### Image Translation
- Original image is displayed  
![alt text](<Screenshot 2026-08-05 100439.png>)
- Translated image (shifted right and down) is displayed 
 ![alt text](<Screenshot 2026-08-05 100449.png>)

### Image Scaling
- Original image is displayed  
- Downscaled image (0.5×) is displayed  
- Upscaled image (2×) is displayed  
![alt text](<Screenshot 2026-08-05 101510.png>)

### Image Shearing
- Original image is displayed  
- Horizontally sheared image is displayed  
- Vertically sheared image is displayed  
![alt text](<Screenshot 2026-08-05 100502.png>)

### Image Reflection
- Original image is displayed  
- Horizontally flipped image is displayed  
- Vertically flipped image is displayed  
- Both-axis flipped image is displayed  
![alt text](<Screenshot 2026-08-05 100512.png>)

### Image Rotation
- Original image is displayed  
- 45° rotated image is displayed  
- 90° rotated image is displayed  
![alt text](<Screenshot 2026-08-05 100526.png>)

### Image Cropping
- Original image is displayed
- Cropped image is displayed
![alt text](<Screenshot 2026-08-05 100540.png>)

---

##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
