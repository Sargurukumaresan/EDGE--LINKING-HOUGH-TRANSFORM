# EDGE-LINKING-USING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using the Canny operator from cv2, detect the edges of the images.

### Step5:
Using the houghlinesP(), detect the line co-ordinates for every points in the images. Using for loop, draw the lines on the found co-ordinates. Display the image.


## Program:
```
DEVELOPED BY: SARGURU.K
REGISTER NUMBER:212222230134
```

# Read image and convert it to grayscale image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('dip21.jpg',0)
plt.imshow(image1)
img= cv2.GaussianBlur(image1,(3,3),0)
plt.imshow(img)
```


# Find the edges in the image using canny detector and display
```
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()
```

# Detect points that form a line using HoughLinesP
```

lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)
```


# Draw lines on the image
```
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(edges1,(x1, y1),(x2, y2),(255,0,0),3)

```

# Display the result

```
plt.imshow(edges1)

```
## Output

### Input image 
![Screenshot from 2023-09-26 22-34-14](https://github.com/Dhanudhanaraj/EDGE--LINKING-HOUGH-TRANSFORM/assets/119218812/a36a8471-b167-43fe-9a64-81b6683996ba)


### Grayscale image
![Screenshot from 2023-09-26 22-34-22](https://github.com/Dhanudhanaraj/EDGE--LINKING-HOUGH-TRANSFORM/assets/119218812/bdea6733-a7ae-48a4-b7ec-39c24bd792b1)


### Canny Edge detector output
![Screenshot from 2023-09-26 22-34-28](https://github.com/Dhanudhanaraj/EDGE--LINKING-HOUGH-TRANSFORM/assets/119218812/6d9bebfd-d839-4ab0-9a92-9a0b349db116)



### Display the result of Hough transform

![Screenshot from 2023-09-26 22-34-35](https://github.com/Dhanudhanaraj/EDGE--LINKING-HOUGH-TRANSFORM/assets/119218812/5195a7bf-8c7f-4a28-adce-7f382f047e5f)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
