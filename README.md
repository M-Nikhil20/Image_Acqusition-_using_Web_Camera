
### Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1:
Import required libraries.
<br>

### Step 2:
Create an instance of video capture object and capture the video through your webcam.
<br>

### Step 3:
Display the image and then resize the window to display the smaller sized image. 
<br>

### Step 4:
Rotate the image and display it.
<br>

### Step 5: 
End the program.
<br>

## Program:

``` Python
### Developed By: M Nikhil
### Register No: 212222230095

## i) Write the frame as JPG file

import cv2
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()


## ii) Display the video

import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


## iii) Display the video by resizing the window

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


## iv) Rotate and display the video

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()


```
## Output

### i) Write the frame as JPG image

![image](https://github.com/user-attachments/assets/bbfad0e2-0db7-44e8-accf-69040194d22f)

### ii) Display the video

![image](https://github.com/user-attachments/assets/be275cbd-fdb1-40f6-bc5d-20d67f5e1df3)

### iii) Display the video by resizing the window

![image](https://github.com/user-attachments/assets/e67f0627-37cc-4856-bbf2-cbe3bab755dc)

### iv) Rotate and display the video

![image](https://github.com/user-attachments/assets/2c369be0-d75e-422a-8682-379436bd36e4)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
