# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using a function warpPerpective()

### Step3:
Scale the image by multiplying the rows and columns with a float value.

### Step4:
Shear the image in both the rows and columns.

### Step5:
Find the reflection of the image.

### Step6 :
Rotate the image using angle function.

## Program:
```
# Developed By:KAVI NILAVAN DK 
# Register Number: 212223230103

import cv2
import numpy as np

# Load the image (Corrected path - use raw string)
image = cv2.imread(r"C:\Users\admin\Downloads\imgage1.webp")  # Make sure the file exists
(h, w) = image.shape[:2]

# ----------------------- Translation -----------------------
# Move image 100 pixels right and 50 pixels down
tx, ty = 100, 50
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])
translated = cv2.warpAffine(image, translation_matrix, (w, h))

# ----------------------- Scaling -----------------------
# Resize by 1.5x horizontally and 0.75x vertically
scaled = cv2.resize(image, None, fx=1.5, fy=0.75, interpolation=cv2.INTER_LINEAR)

# ----------------------- Shearing -----------------------
# Shear image horizontally
shear_matrix = np.float32([[1, 0.5, 0], [0, 1, 0]])  # x-shear
sheared = cv2.warpAffine(image, shear_matrix, (int(w + 0.5 * h), h))

# ----------------------- Reflection (Flipping) -----------------------
# Flip horizontally (mirror image)
h_flip = cv2.flip(image, 1)
# Flip vertically
v_flip = cv2.flip(image, 0)

# ----------------------- Rotation -----------------------
# Rotate by 45 degrees around the center
angle = 45
scale = 1.0
center = (w // 2, h // 2)
rotation_matrix = cv2.getRotationMatrix2D(center, angle, scale)
rotated = cv2.warpAffine(image, rotation_matrix, (w, h))

# ----------------------- Cropping -----------------------
# Crop a region (top-left 200x200)
cropped = image[0:200, 0:200]

# ----------------------- Display Results -----------------------
cv2.imshow("Original", image)
cv2.imshow("Translated", translated)
cv2.imshow("Scaled", scaled)
cv2.imshow("Sheared", sheared)
cv2.imshow("Horizontally Flipped", h_flip)
cv2.imshow("Vertically Flipped", v_flip)
cv2.imshow("Rotated", rotated)
cv2.imshow("Cropped", cropped)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:
### Original Image:

![image](https://github.com/user-attachments/assets/40080bee-fa34-48a7-aa3d-ffb816ecd3a1)

### i)Image Translation

![image](https://github.com/user-attachments/assets/fcab6781-7b2d-4a4a-8a12-287ce944b088)


### ii) Image Scaling

![image](https://github.com/user-attachments/assets/7be3fab8-eb41-4264-b333-3138e7cb6a4f)


### iii)Image shearing

![image](https://github.com/user-attachments/assets/11412d26-5316-42cb-a64f-a82c8273000a)


### iv)Image Reflection
#### i) Horizontally Flipped:

![image](https://github.com/user-attachments/assets/d02d4205-f733-45f7-8f92-a664f19c4d36)

#### ii) Vertically Flipped:
![image](https://github.com/user-attachments/assets/3ec73e83-9539-4c74-9982-fe12d6bc8b16)

### v)Image Rotation

![image](https://github.com/user-attachments/assets/ffecdd14-2294-404e-9aca-22b62b148911)


### vi)Image Cropping

![image](https://github.com/user-attachments/assets/131d38f8-c8d8-4955-a1ef-00d7a52235a2)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
