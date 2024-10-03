# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>Import all the necessary modules

### Step2:
<br>Choose an image and save it as filename.jpg

### Step3:
<br>Use imread to read the image

### Step4:
<br>Use cv2.warpPerspective(image,M,(cols,rows)) to translation the image

### Step5:
<br>Use cv2.warpPerspective(image,M,(cols*2,rows*2)) to scale the image
### Step6:
Use cv2.warpPerspective(image,M,(int(cols*1.5),int(rows*1.5))) for x and y axis to shear the image

### Step7:
<br>Use cv2.warpPerspective(image,M,(int(cols),int(rows))) for x and y axis to reflect the image
### Step8:
<br>Use cv2.warpPerspective(image,M,(int(cols),int(rows))) to rotate the image
### Step9:
<br>Crop the image to remove unwanted areas from an image
### Step10:

<br>Use cv2.imshow to show the image
### Step11:
<br>End the program
## Program:

### Developed By: Sachin.C
### Register Number: 212222230125
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('skull.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib
plt.subplot()
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/5a7df274-0f7b-4291-ad60-cb15752cb000)

### i)Image Translation
```python
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.subplot()
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/c800c23e-a510-4ce0-a351-10a7014ec5d7)

### ii) Image Scaling
```python
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x
plt.subplot()
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/93b9f998-55a3-4e19-82e7-493512f13d31)

### iii)Image shearing
```python
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.subplot()
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/fe99cb6b-e41a-4a48-82cb-abd2f1c7692a)

### iv)Image Reflection
```python
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.subplot()
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/276b4936-1850-4060-870a-051321a07f35)

### v)Image Rotation
```python
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.subplot()
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/eca51447-7d55-44eb-b1ea-d68142d778df)

### vi)Image Cropping
```python
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/0a54b788-a3b7-4a56-b876-ab895b443db9)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
