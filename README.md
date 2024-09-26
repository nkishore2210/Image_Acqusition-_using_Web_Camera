# Image Acqusition Using Web Camera

## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import the cv2 and numpy package.
### Step 2:
Read the Video frame using the cv2.VideoCapture(0)
### Step 3:
Write the image using imwrite().
### Step 4:
Display the frame using the imshow().
### Step 5:
Divide the frame into halves and assign the smaller frame

## Program:
### Developed By: KISHORE N
### Register No: 212222240049

## i) Write the frame as JPG file
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('tr',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('tr',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Rotated Video',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
![Screenshot 2024-09-26 160837](https://github.com/user-attachments/assets/626cabfd-880a-4930-8e14-a4ad0be03b73)

### ii) Display the video
![Screenshot 2024-09-26 160837](https://github.com/user-attachments/assets/e1db4215-9cd5-4840-99ab-d5bd0d05f684)

### iii) Display the video by resizing the window
![Screenshot 2024-09-26 160925](https://github.com/user-attachments/assets/d887d048-6964-4388-b915-0f873e59d07b)

### iv) Rotate and display the video
![Screenshot 2024-09-26 160948](https://github.com/user-attachments/assets/804dd9e1-723c-43a0-8674-c16eaec5815a)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
