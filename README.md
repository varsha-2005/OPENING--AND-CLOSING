
# OPENING AND CLOSING

## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required

1. Anaconda - Python 3.7
2. OpenCV

## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText

### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation
 
## Program:
#### Developed by:M.Pranathi
#### Register.no:212222230166
## Import the necessary packages

```python
import cv2
import numpy as np
from matplotlib import pyplot as plt
```
## Create the Text using cv2.putText

```python
# Read the color image
input_image_path = 'peacock.jpg'
color_image = cv2.imread(input_image_path)

# Convert the color image to grayscale
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)

# Perform edge detection using Canny
edges = cv2.Canny(gray_image, 100, 200)  # you can adjust the thresholds as needed

# Define the kernel size for erosion and dilation
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)

# Perform erosion
erosion = cv2.erode(edges, kernel, iterations=1)

# Perform dilation
dilation = cv2.dilate(edges, kernel, iterations=1)

# Perform opening
opening = cv2.morphologyEx(edges, cv2.MORPH_OPEN, kernel)

# Perform closing
closing = cv2.morphologyEx(edges, cv2.MORPH_CLOSE, kernel)
```


## Create the structuring element

```python
plt.figure(figsize=(15, 10))
plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')
```


## Use Opening operation

```python
plt.subplot(2, 3, 2)
plt.imshow(opening, cmap='gray')
plt.title('Opening')
plt.axis('on')
```



## Use Closing Operation

```python
plt.subplot(2, 3, 3)
plt.imshow(closing, cmap='gray')
plt.title('Closing')
plt.axis('on')

plt.show()

```
## Output:
### Display the input Image

![oi](https://github.com/JananiSoundararajan/OPENING--AND-CLOSING/assets/119477549/714739ae-6d72-4dd0-9fb7-71af939f2f2b)

### Display the result of Opening

![opi](https://github.com/JananiSoundararajan/OPENING--AND-CLOSING/assets/119477549/ed78bee0-8402-4702-91d5-af73fd030af4)

### Display the result of Closing

![ci](https://github.com/JananiSoundararajan/OPENING--AND-CLOSING/assets/119477549/288a27cf-4cdf-459f-8fb9-504eecce1362)

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
