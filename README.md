# Image_Acqusition-_using_Web_Camera
## Aim
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:
``` Python
### Developed By: SANJAYKUMAR N B
### Register No: 212223230189
```

## i) Write the frame as JPG file
```Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
ret,frame = videoCaptureObject.read()
cv2.imshow('DAP',frame)
if cv2.waitKey(1) == ord('q'):
break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```Python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
ret,frame = videoCaptureObject.read()
cv2.imshow('DAP',frame)
if cv2.waitKey(1) == ord('q'):
break
videoCaptureObject.release()
cv2.destroyAllWindows()

```
## iii) Display the video by resizing the window
```Python
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
image [height//2:, width//2:] = smaller_frame
cv2.imshow('DAP', image)
if cv2.waitKey(1) == ord('q'):
break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```Python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
ret, frame = cap.read()
width = int(cap.get(3))
height = int(cap.get(4))
image = np.zeros(frame.shape, np.uint8)
smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[:height//2, width//2:] = smaller_frame
image [height//2:, width//2:] = smaller_frame
cv2.imshow('DAP', image)
if cv2.waitKey(1) == ord('q'):
break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
![Screenshot 2024-03-06 234725](https://github.com/Adhithya4116/Image_Acqusition-_using_Web_Camera/assets/118707079/bbfab5a5-8d15-40b2-98e0-a89447a328d9)
</br>
</br>

### ii) Display the video
![Screenshot 2024-03-06 235426](https://github.com/Adhithya4116/Image_Acqusition-_using_Web_Camera/assets/118707079/7454c2a5-12c3-4fe2-8182-286db3acf834)

</br>
</br>

### iii) Display the video by resizing the window
![Screenshot 2024-03-06 235535](https://github.com/Adhithya4116/Image_Acqusition-_using_Web_Camera/assets/118707079/1350b2b2-36e4-4d1a-a5f5-ebd87bd15fbe)
</br>
</br>

### iv) Rotate and display the video
![Screenshot 2024-03-06 235625](https://github.com/Adhithya4116/Image_Acqusition-_using_Web_Camera/assets/118707079/6cdc4f9c-5953-41ae-ab3d-e85f35e61b4f)
</br>
</br>

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
