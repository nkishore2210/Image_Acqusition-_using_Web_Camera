
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
 
### Developed By: SANJAY M
### Register No: 212222240090

## i) Write the frame as JPG file
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('str',frame)
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
    cv2.imshow('str',frame)
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

![Screenshot 2024-09-26 153618](https://github.com/user-attachments/assets/969c6783-2314-4d40-b891-5497953c78c5)


### ii) Display the video

![Screenshot 2024-09-26 153618](https://github.com/user-attachments/assets/f693791b-3571-460d-8791-b9713c2fd594)


### iii) Display the video by resizing the window

![Screenshot 2024-09-26 153656](https://github.com/user-attachments/assets/345af85a-686c-4ee7-aed9-e1f7ca194fb2)



### iv) Rotate and display the video

![Screenshot 2024-09-26 153728](https://github.com/user-attachments/assets/4e2be0ea-1169-49b8-974a-0958db4d844a)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
