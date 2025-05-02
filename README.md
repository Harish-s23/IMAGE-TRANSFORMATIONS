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
```# Developed By: HARESH R
# Register Number: 212224040097

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

![Screenshot 2025-05-02 231556](https://github.com/user-attachments/assets/6120616f-17ed-4fed-9f63-1e0cb838349e)

### i)Image Translation

![Screenshot 2025-05-02 231617](https://github.com/user-attachments/assets/8b17dc19-8e2a-4e08-a40d-eb2a1c6d169a)


### ii) Image Scaling

![Screenshot 2025-05-02 231632](https://github.com/user-attachments/assets/487fc16b-ff96-4a22-9cce-0f228ccd53a9)


### iii)Image shearing

![Screenshot 2025-05-02 231645](https://github.com/user-attachments/assets/99a470a9-b801-47ea-bc03-29550c0776e3)


### iv)Image Reflection
#### i) Horizontally Flipped:
![Screenshot 2025-05-02 231701](https://github.com/user-attachments/assets/a538b1fd-a3ad-4637-a56c-8aabdc1fe6dd)


#### ii) Vertically Flipped:
![Screenshot 2025-05-02 231714](https://github.com/user-attachments/assets/bb10e3d9-8243-4e0d-8c65-1e2f6e3c5f14)

### v)Image Rotation

![Screenshot 2025-05-02 231727](https://github.com/user-attachments/assets/21027370-e5d5-4b80-a036-000ca2179d0c)


### vi)Image Cropping
![Screenshot 2025-05-02 231742](https://github.com/user-attachments/assets/a51533fc-a333-4882-928c-0282750cdff8)



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
