# IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1: 
Import numpy module as np and pandas as pd.
### Step 2: 
Assign the values to variables in the program.
### Step 3: 
Get the values from the user appropriately.
### Step 4: 
Continue the program by implementing the codes of required topics.
### Step 5: 
Thus the program is executed in google colab.

## Program:

#### Developed By : PRAVEEN S
#### Register Number : 212222240078

### Installing OpenCV , importing necessary libraries and displaying images  

```py
# Install OpenCV library
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images 
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

```

#### (i) Image Translation
```py
# Load an image from URL or file path
image_url = '1.jpg'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)
```

#### (ii) Image Scaling
```py

# Load an image from URL or file path
image_url = '2.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis


# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("Original Image:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)

```




#### (iii) Image shearing
```py
# Load an image from URL or file path
image_url = '3.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)

```



#### (iv) Image Reflection

```py
# Load an image from URL or file path
image_url = '4.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

```

##### (a) → Reflecting Horizontally

```py
# Display original and reflected images

show_image(image)
print("↑ Original Image")
show_image(reflected_image_horizontal)
print("↑ Reflected Horizontally")
```

##### (b) → Reflected Vertically

```py
show_image(image)
print("↑ Original Image")
show_image(reflected_image_vertical)
print("↑ Reflected Vertically")

```

##### (c) → Reflecting Horizontally & Vertically
```py

show_image(image)
print("↑ Original Image")
show_image(reflected_image_both)
print("↑ Reflected Both")

```

### (v) Image Rotation

```py
# Load an image from URL or file path
image_url = '5.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)

```



### (vi) Image Cropping

```py
# Load an image from URL or file path
image_url = '6.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)

```


## Output:

### (i) Image Translation

![image](https://github.com/Praveen0500/IMAGE-TRANSFORMATIONS/assets/120218611/f8e56b2f-d9da-48d2-86c5-95a53c2d2e2b)

### (ii) Image Scaling

![image](https://github.com/Praveen0500/IMAGE-TRANSFORMATIONS/assets/120218611/1480f7eb-c6fe-43bf-9e8a-352a6bb88e15)

### (iii) Image shearing

![image](https://github.com/Praveen0500/IMAGE-TRANSFORMATIONS/assets/120218611/71270dd6-e4a3-4f8d-ac41-bba38cf09c8b)

### (iv) Image Reflection

#### Reflecting Horizontally

![image](https://github.com/Praveen0500/IMAGE-TRANSFORMATIONS/assets/120218611/b00b6960-0169-495c-800d-a0d8fc169049)

#### Reflecting Vertically

![image](https://github.com/Praveen0500/IMAGE-TRANSFORMATIONS/assets/120218611/b5f62a6b-537e-49e2-9413-7da016ec9829)

#### Reflecting Horizontally & Vertically

![image](https://github.com/Praveen0500/IMAGE-TRANSFORMATIONS/assets/120218611/673cb10a-006a-43ed-a6be-2b7e7424a3ae)

### (v) Image Rotation

![image](https://github.com/Praveen0500/IMAGE-TRANSFORMATIONS/assets/120218611/7e4dff0d-cbf2-452e-bbcc-7345cb5933d2)

### (vi) Image Cropping

![image](https://github.com/Praveen0500/IMAGE-TRANSFORMATIONS/assets/120218611/c857727c-34e7-468d-a6ed-c5da64012fbf)

## Result: 

### Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.






Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
