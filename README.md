# EXP.4-RECORD-IMAGE-TRANSFORMATIONS

## AIM

To write a Python program using OpenCV to perform various image transformations such as translation, scaling, shearing, reflection, rotation, and cropping.

The program performs the following operations:

- Read and display the original image.
- Perform image translation by shifting the image horizontally and vertically.
- Apply image scaling to resize the image.
- Perform image shearing in both horizontal and vertical directions.
- Apply image reflection using flipping.
- Rotate the image by 45 degrees.
- Crop a specific portion of the image.

## SOFTWARE REQUIRED

Anaconda – Python 3.7  
Jupyter Notebook / VS Code  
OpenCV (cv2)  
NumPy  
Matplotlib

## ALGORITHM

**Step 1:**

Import the required libraries: OpenCV, NumPy, and Matplotlib.

**Step 2:**

Read the input image `Image.png` using OpenCV.

**Step 3:**

Display the original image using Matplotlib after converting the BGR image into RGB format.

**Step 4:**

Perform image translation by creating a translation matrix with horizontal shift of 100 pixels and vertical shift of 50 pixels.

**Step 5:**

Apply image scaling using `cv2.resize()` with scaling factors of 5.0 and 2.0.

**Step 6:**

Perform image shearing by creating a shearing matrix with a factor of 0.5 in both horizontal and vertical directions.

**Step 7:**

Perform image reflection using `cv2.flip()`.

**Step 8:**

Perform image rotation by 45 degrees using `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`.

**Step 9:**

Perform image cropping by selecting a specific region from the original image using array slicing.

**Step 10:**

Display all the transformed images using Matplotlib.

## PROGRAM

**Developed By**

## Name: Rubasri R
## Register No: 212224240139

### 1. Import the Required Libraries and Read the Image

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('Image.png')

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
```

**OUTPUT:**

<img width="352" height="455" alt="image" src="https://github.com/user-attachments/assets/26c01dcf-49d6-4ad6-8b07-4d80816fc8e9" />


### 2. Perform Image Translation

```python
tx, ty = 100, 50

M_translation = np.float32([[1, 0, tx], [0, 1, ty]])

translated_image = cv2.warpAffine(
    image, M_translation,
    (image.shape[1], image.shape[0])
)

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')
```

**OUTPUT:**

<img width="380" height="467" alt="image" src="https://github.com/user-attachments/assets/29172f7f-8e6d-4d21-9a60-32c9c9316f30" />



### 3. Perform Image Scaling

```python
fx, fy = 5.0, 2.0

scaled_image = cv2.resize(
    image, None, fx=fx, fy=fy,
    interpolation=cv2.INTER_LINEAR
)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))
plt.title("Scaled Image")
plt.axis('off')
```

**OUTPUT:**

<img width="566" height="307" alt="image" src="https://github.com/user-attachments/assets/86fc9a15-718e-43d1-999a-74f0a2774947" />

### 4. Perform Image Shearing

```python
shear_matrix = np.float32([
    [1, 0.5, 0],
    [0.5, 1, 0]
])

sheared_image = cv2.warpAffine(
    image, shear_matrix,
    (image.shape[1], image.shape[0])
)

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('off')
```

**OUTPUT:**

<img width="385" height="455" alt="image" src="https://github.com/user-attachments/assets/7c84ff19-af5f-4817-a34f-7bc8e65c169b" />


### 5. Perform Image Reflection

```python
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")
plt.axis('off')
```

**OUTPUT:**

<img width="361" height="446" alt="image" src="https://github.com/user-attachments/assets/e18a2e27-3638-4c01-ab33-827bbae3e9cf" />



### 6. Perform Image Rotation

```python
(height, width) = image.shape[:2]

angle = 45

center = (width // 2, height // 2)

M_rotation = cv2.getRotationMatrix2D(center, angle, 1)

rotated_image = cv2.warpAffine(
    image, M_rotation, (width, height)
)

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')
```

**OUTPUT:**

<img width="382" height="453" alt="image" src="https://github.com/user-attachments/assets/d73b479c-26da-48ec-a127-2403bdd7e8d7" />



### 7. Perform Image Cropping

```python
x, y, w, h = 200, 200, 250, 200

cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title("Cropped Image")
plt.axis('off')
```

**OUTPUT:**

<img width="388" height="457" alt="image" src="https://github.com/user-attachments/assets/49381911-c8af-482c-a36b-811cb9b91825" />




## RESULT

Thus, various image transformations such as translation, scaling, shearing, reflection, rotation, and cropping are successfully performed using OpenCV. The transformations demonstrate how images can be modified and manipulated for different image processing applications.
