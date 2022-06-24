# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
<br>
Import cv2 and capture the video using cv2.VideoCapture(0)

### Step 2:
<br>
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)

### Step 3:
<br>
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)


### Step 4:
<br>
Display the image until the loop gets over

### Step 5:
<br>
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)

## Program:
``` Python
### Developed By: Thenmozhi P
### Register No:212221230116


## i) Write the frame as JPG file

import cv2

videoCaptureObject = cv2.VideoCapture(0)


while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()

## ii) Display the video

import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret,frame = cap.read()
    cv2.imshow('Frame',frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window

import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video

import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame


    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()










```
## Output

### i) Write the frame as JPG image

(https://user-images.githubusercontent.com/95198708/175481529-a3fbd226-8432-4c1b-bd7a-c191466323a3.png)



### ii) Display the video
(https://user-images.githubusercontent.com/95198708/175481624-e4e7f9a1-56ef-4d65-bd08-1e6e5eb554e6.png)



### iii) Display the video by resizing the window
(https://user-images.githubusercontent.com/95198708/175481671-715cd54e-9a1e-4296-9bbd-5bf54a1e2eed.png)




### iv) Rotate and display the video
(https://user-images.githubusercontent.com/95198708/175481712-a06d81e8-a164-4087-a3c8-621e833b29b2.png)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
