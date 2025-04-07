
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
Import CV2,numpy and the other required libraries 
<br>

### Step 2:
Create an instance of Video Capture and save the displayed image
<br>

### Step 3:
Capture video and using numpy resize the shape of the window and display the video 
<br>

### Step 4:
Rotate the captured image by 180*
<br>

### Step 5:
<br>

## Program:
```
## Developed By: MOHAMED RASHITH S
## Register No: 212223243003

## i) Write the frame as JPG file

import cv2
obj = cv2.VideoCapture(0)
while True:
    cap,frame = obj.read()
    if not cap:
        break
    cv2.imshow('video',frame)
    cv2.imwrite('picture.jpg',frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()

## ii) Display the video

img = cv2.VideoCapture(0)
while True:
    image,frame = img.read()
    cv2.imshow('pic',frame) 
    if cv2.waitKey(1)==ord('q'):
        break
img.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window

import numpy as np
capture = cv2.VideoCapture(0)
while True:
    ret,frame=capture.read()
    if not ret:
        break
    height,width = frame.shape[:2]
    smaller_frame=cv2.resize(frame,(width//2,height//2))
    image = np.zeros((height,width,3),dtype=np.uint8)
    image[:height//2,:width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame

    cv2.imshow('PIC',smaller_frame)
    
    if cv2.waitKey(1)==ord('q'):
        break
capture.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video

capture = cv2.VideoCapture(0)
while True:
    ret,frame=capture.read()
    if not ret:
        break
    height,width = frame.shape[:2]
    smaller_frame = cv2.resize(frame,(width//2,height//2))
    image = np.zeros((height,width,3),dtype=np.uint8)

    image[:height//2,:width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    
    cv2.imshow('ROTATE_PIC',image)
    if cv2.waitKey(1) == ord('q'):
        break
capture.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
</br>

![Screenshot 2025-03-29 134416](https://github.com/user-attachments/assets/fb7020e6-ef8f-4c51-af9f-fe7ba296c6cd)

</br>


### ii) Display the video
</br>

![Screenshot 2025-03-29 134843](https://github.com/user-attachments/assets/d26f118f-52cf-4c86-984c-384029152895)
</br>


### iii) Display the video by resizing the window
</br>

![Screenshot 2025-03-29 135008](https://github.com/user-attachments/assets/14d1cf94-bf23-4eac-b880-0b4b60edff15)
</br>



### iv) Rotate and display the video
</br>



![Screenshot 2025-03-29 135100](https://github.com/user-attachments/assets/ff79c0a6-cd02-4bd0-9c31-130f567d3c3c)

</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
