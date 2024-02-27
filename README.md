# Image_Acqusition-_using_Web_Camera
## Aim
 
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG.

ii) Display the video.

iii) Display the video by resizing the window.

iv) Rotate and display the video.

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import the cv2 and numpy package.

### Step 2:
Read the Video frame using the cv2.VideoCapture(0).

### Step 3:
Write the image using imwrite().

### Step 4:
Display the frame using the imshow().

### Step 5:
Divide the frame into halves and assign the smaller frame.

### Step 6:
Rotate the frame using the cv2.rotate().

## Program
```py
### Developed By: ARSHATHA P
### Register No: 212222230012
```

## i) Write the frame as JPG file
```py
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("ARSHA.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```

## ii) Display the video
```py
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('ARSHA',frame)
    cv2.imwrite("butterfly.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window
```py
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
    cv2.imshow('ARSHA ',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```py
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
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('ARSHA', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image

![2 01](https://github.com/arshatha-palanivel/Image_Acqusition-_using_Web_Camera/assets/118682484/06cf7512-af34-4702-ad60-84ab961c34e3)


### ii) Display the video

![2 02](https://github.com/arshatha-palanivel/Image_Acqusition-_using_Web_Camera/assets/118682484/2bb50b71-3c95-499d-b809-dd63818b2a64)


### iii) Display the video by resizing the window

![2 03](https://github.com/arshatha-palanivel/Image_Acqusition-_using_Web_Camera/assets/118682484/68f9d65e-7b77-4602-9fb4-8d2217be1c7a)


### iv) Rotate and display the video

![2 04](https://github.com/arshatha-palanivel/Image_Acqusition-_using_Web_Camera/assets/118682484/441a5b33-23b0-4153-aa8f-e0908163678d)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
