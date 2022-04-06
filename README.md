# Image-Acquisition-from-Web-Camera
## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1
Use VideoCapture(0) to access web camera

### Step 2:
Use imread to read the video or image

### Step 3:
Use imwrite to save the image

### Step 4:
Use imshow to show the video

### Step 5:
End the program and close the output video windows by pressing 'q'.
## Program:
``` Python
### Developed By: Sri Harish M
### Register No:212220230047

## i) Write the frame as JPG file

import cv2

videoCaptureObject = cv2.VideoCapture(0)


while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("New.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()





## ii) Display the video

import cv2

videoCaptureObject = cv2.VideoCapture(0)


while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('image', frame)
    
    if cv2.waitKey(1) == ord('k'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()




## iii) Display the video by resizing the window

import cv2
import numpy as np

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
videoCaptureObject.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video

import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)


    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)


    image[height//2:, width//2:] = smaller_frame
    

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()


```
## Output

### i) Write the frame as JPG image
![h1](https://user-images.githubusercontent.com/75241366/161988438-9c8351f9-52fc-439e-bb72-32ec8856a5e2.jpg)


### ii) Display the video
![h2](https://user-images.githubusercontent.com/75241366/161988454-2ead0021-862d-4488-9120-ce907e96a928.jpg)

### iii) Display the video by resizing the window
![h3](https://user-images.githubusercontent.com/75241366/161988475-9ad8cac1-b1cf-42ba-9efb-bcf86200b1e3.jpg)


### iv) Rotate and display the video
![h4](https://user-images.githubusercontent.com/75241366/161988495-bbfd4c4b-e76b-4c45-8e65-dbf3b2ec6f6b.jpg)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
