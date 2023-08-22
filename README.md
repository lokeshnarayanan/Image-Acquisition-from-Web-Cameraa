# Image-Acquisition-from-Web-Cameraa
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

Import cv2 and capture the viedo using cv2.ViedoCapture(0).

### Step 2:

Write the capture image using cv2.imwrite("NewPicture.jpeg",frame).
### Step 3:


Resize the image using cv2.resize(frame,(0,0),fx=0.5,fy=0.5).

### Step 4:

Display the image until the loop gets over.

### Step 5:

Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180).

## Program:
``` Python
### Developed By:Lokesh N
### Register No:212222100023

## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("NewPicture.jpeg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video

```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('lokesh',frame)
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
    cv2.imshow('lokesh',image)
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
    cv2.imshow('lokesh',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```








## Output

### i) Write the frame as JPG image

![lokesh1](https://github.com/lokeshnarayanan/Image-Acquisition-from-Web-Cameraa/assets/119393019/af9becbe-72c2-4f04-a4e4-704c069af231)




### ii) Display the video

![Screenshot from 2023-08-22 20-43-51](https://github.com/lokeshnarayanan/Image-Acquisition-from-Web-Cameraa/assets/119393019/957a876b-fd23-444f-b4d2-6e2857c13863)



### iii) Display the video by resizing the window

![1](https://github.com/lokeshnarayanan/Image-Acquisition-from-Web-Cameraa/assets/119393019/6f25fa55-8985-42b1-bca0-c55627db16f4)






### iv) Rotate and display the video

![lokesh](https://github.com/lokeshnarayanan/Image-Acquisition-from-Web-Cameraa/assets/119393019/4b07e3c8-9f69-4c6b-acbb-1c717dd2c0bd)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
