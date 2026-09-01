# Image Segmentation Using Thresholding Techniques in OpenCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

- Global Thresholding
- Adaptive Thresholding
- Otsu's Thresholding

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Load the input image using OpenCV.

### Step 3:

Convert the input image into grayscale format.

### Step 4: Global Thresholding

- Select a fixed threshold value.
- Apply thresholding to separate foreground and background pixels.
- Display the thresholded image.

### Step 5: Adaptive Thresholding

- Compute threshold values for small regions of the image.
- Apply Adaptive Mean Thresholding.
- Apply Adaptive Gaussian Thresholding.
- Display the segmented images.

### Step 6: Otsu's Thresholding

- Automatically determine the optimal threshold value.
- Apply Otsu's thresholding technique.
- Display the segmented image.

### Step 7:

Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

## Program

## Developed By

**Name:** SUPRIYA PRABHU

**Register No:** 212224240165

## Output

### Original Grayscale Image

- The grayscale version of the input image is displayed.
- Serves as the input for thresholding operations.
```
  import cv2
import matplotlib.pyplot as plt

img = cv2.imread(r"C:\Users\admin\Pictures\Screenshots\Screenshot 2026-08-25 030722.png")

if img is None:
    print("Error: Image not found. Check the file path.")
else:
    img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
    plt.imshow(img_rgb)
    plt.title("Original Image")
    plt.axis("off")
    plt.show()
```
   <img width="516" height="346" alt="image" src="https://github.com/user-attachments/assets/53c4edc2-1507-4503-8f50-c41985c6e23e" />

```

import cv2
import matplotlib.pyplot as plt
img = cv2.imread(r"C:\Users\admin\Pictures\Screenshots\Screenshot 2026-08-25 030722.png", cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")
plt.show()
```

<img width="516" height="346" alt="image" src="https://github.com/user-attachments/assets/4b68aa77-4a98-45af-83b1-a74793c63d7b" />

### Global Thresholding

- Original image is displayed.
- Thresholded image is displayed.
- A fixed threshold value is used for segmentation.
- Pixels are classified as foreground or background.

```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread(r"C:\Users\admin\Pictures\Screenshots\Screenshot 2026-08-25 030722.png", cv2.IMREAD_GRAYSCALE)
_, result = cv2.threshold(img, 127, 255, cv2.THRESH_BINARY)
plt.imshow(result, cmap="gray")
plt.title("Global Thresholding")
plt.axis("off")
plt.show()
```
<img width="516" height="346" alt="image" src="https://github.com/user-attachments/assets/dacc136f-8be7-408e-86fa-b6cef2cc70de" />

### Adaptive Thresholding

- Original image is displayed.
- Adaptive Mean Thresholded image is displayed.
- Adaptive Gaussian Thresholded image is displayed.
- Threshold values vary across different regions of the image.
- Suitable for images with uneven illumination.
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread(r"C:\Users\admin\Pictures\Screenshots\Screenshot 2026-08-25 030722.png", cv2.IMREAD_GRAYSCALE)
result = cv2.adaptiveThreshold(
    img, 255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY,
    11, 2
)
plt.imshow(result, cmap="gray")
plt.title("Adaptive Thresholding")
plt.axis("off")
plt.show()

```
<img width="516" height="346" alt="image" src="https://github.com/user-attachments/assets/eb476c1c-950a-4201-92ca-9dfd6b32eb6e" />

### Otsu's Thresholding

- Original image is displayed.
- Otsu segmented image is displayed.
- Optimal threshold value is calculated automatically.
- Produces improved segmentation for bimodal histograms.
```
import cv2
import matplotlib.pyplot as plt
img = cv2.imread(r"C:\Users\admin\Pictures\Screenshots\Screenshot 2026-08-25 030722.png", cv2.IMREAD_GRAYSCALE)
_, result = cv2.threshold(
    img, 0, 255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)
plt.imshow(result, cmap="gray")
plt.title("Otsu's Thresholding")
plt.axis("off")
plt.show()
```

<img width="516" height="346" alt="image" src="https://github.com/user-attachments/assets/e4c1261d-24c0-4e74-8897-3e17de51dcb8" />


## Result

Thus, image segmentation is successfully performed using **Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding** techniques in OpenCV. 
