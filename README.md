# EXP-2 Image_Acqusition-_using_Web_Camera
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
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.


## Program:
### Developed by: Karthikeyan K
### Reg no: 212223230101

## i) Write the frame as JPG file
``` Python
## Developed By: KAVI NILAVAN DK
## Register No: 212223230103
import cv2
import numpy as np
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("captured_frame.jpg",frame)
viedoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```Python
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cv2.imshow('captured_frame', frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```Python
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000)  
image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```Python
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()

```

## Output

### i) Write the frame as JPG image
<img width="512" height="411" alt="b6006c36-1a02-444a-be0c-02f68f944e67" src="https://github.com/user-attachments/assets/d4cd1105-0c48-4d94-85a9-8c51543cba4d" />

### ii) Display the video
<img width="512" height="389" alt="3e1f6ad3-5efb-40d4-a8f8-24c580c5975f" src="https://github.com/user-attachments/assets/1f9ec87a-5093-44fc-8bc1-bf73e2dbd92b" />


### iii) Display the video by resizing the window

<img width="266" height="389" alt="42cd589b-095b-4eea-a17a-bb344b6adfd7" src="https://github.com/user-attachments/assets/380d06ef-2e13-41f2-ab5f-480d3852749f" />

### iv) Rotate and display the video

<img width="297" height="389" alt="59bbd10c-b4b7-42a3-b92f-11a890e0fcda" src="https://github.com/user-attachments/assets/35a20a41-72fa-4b7d-8aa4-574c66fc0d7b" />

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
