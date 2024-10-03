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
image = cv2.imread('football.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib
plt.subplot()
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```
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
### ii) Image Scaling
```python
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x
plt.subplot()
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
### iii)Image shearing
```python
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.subplot()
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```
### iv)Image Reflection
```python
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.subplot()
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```

### v)Image Rotation
```python
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.subplot()
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```


### vi)Image Cropping
```python
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
## Output:
### i)Image Translation

![image](https://github.com/user-attachments/assets/4ef15972-8c35-41e2-b8bb-2347b51114de)

### ii) Image Scaling

![image](https://github.com/user-attachments/assets/d15362a7-d021-4ecc-8e10-11b9596f4b96)



### iii)Image shearing

![image](https://github.com/user-attachments/assets/35bb3c77-5b42-4def-a375-4f62317543df)



### iv)Image Reflection


![image](https://github.com/user-attachments/assets/69322202-5411-4cf3-9a81-60678398dac0)



### v)Image Rotation

![image](https://github.com/user-attachments/assets/2fc7256f-ffd8-48d4-8482-20bdd92e44e4)



### vi)Image Cropping


![image](https://github.com/user-attachments/assets/54ae65ee-5b99-4a38-9915-a3a48e479d02)



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
