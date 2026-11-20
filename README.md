# EX. No: 10 – IMPLEMENTATION OF OPENING AND CLOSING

## Developed by:
## Name: DAKSHA SUBBAIAN
## Register number:212223230036

## Aim

To implement Opening and Closing morphological operations using Python and OpenCV.

## Software Required

1. Anaconda – Python 3.7
2. OpenCV
3. NumPy
4. Matplotlib

## Algorithm

### Step 1:
Import the necessary packages such as OpenCV, NumPy, and Matplotlib.

### Step 2:
Create a blank image using NumPy and insert the text "Open and Close" using OpenCV's `cv2.putText()` function.

### Step 3:
Create a 3 × 3 structuring element (kernel) using NumPy.

### Step 4: Opening Operation
Apply the Opening operation using `cv2.morphologyEx()` with `cv2.MORPH_OPEN`. Opening performs erosion followed by dilation to remove small foreground noise.

### Step 5: Closing Operation
Apply the Closing operation using `cv2.morphologyEx()` with `cv2.MORPH_CLOSE`. Closing performs dilation followed by erosion to fill small gaps and holes in foreground objects.

## Program

```python
# Step 1: Import the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Create the text using cv2.putText
image = np.zeros((500, 500, 3), dtype=np.uint8)

font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(
    image,
    'Open and Close',
    (100, 250),
    font,
    1,
    (255, 255, 255),
    2,
    cv2.LINE_AA
)

# Step 3: Create the structuring element
kernel = np.ones((3, 3), np.uint8)

# Display the input image
plt.figure(figsize=(5, 5))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image with Text")
plt.axis('off')
plt.show()

# Step 4: Use Opening operation
# Opening is erosion followed by dilation
opened_image = cv2.morphologyEx(
    image,
    cv2.MORPH_OPEN,
    kernel
)

# Display the result of Opening
plt.figure(figsize=(5, 5))
plt.imshow(cv2.cvtColor(opened_image, cv2.COLOR_BGR2RGB))
plt.title("Opening Operation")
plt.axis('off')
plt.show()

# Step 5: Use Closing operation
# Closing is dilation followed by erosion
closed_image = cv2.morphologyEx(
    image,
    cv2.MORPH_CLOSE,
    kernel
)

# Display the result of Closing
plt.figure(figsize=(5, 5))
plt.imshow(cv2.cvtColor(closed_image, cv2.COLOR_BGR2RGB))
plt.title("Closing Operation")
plt.axis('off')
plt.show()
```

## Output

<img width="482" height="510" alt="image" src="https://github.com/user-attachments/assets/95b98922-35d6-4312-b92e-aa47ed91654f" />

<img width="477" height="507" alt="image" src="https://github.com/user-attachments/assets/e035299d-17d0-413b-b536-2154adaf0bfa" />

## Result

Thus, the Opening and Closing morphological operations are successfully implemented using Python and OpenCV.

