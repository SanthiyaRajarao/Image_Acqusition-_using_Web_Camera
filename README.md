
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
<br> Import the cv2 and numpy package.

### Step 2:
<br> Read the Video frame using the cv2.VideoCapture(0)

### Step 3:
<br> Write the image using imwrite()

### Step 4:
<br> Display the frame using the imshow().

### Step 5:
<br> Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:
### Developed By: SANTHIYA R
### Register No: 212223230192

## i) Write the frame as JPG file

```
import cv2
import numpy as np
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```

## ii) Display the video

```
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('pic',frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()

```

## iii) Display the video by resizing the window

```
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
    cv2.imshow('PIC',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```


## iv) Rotate and display the video



```

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
    cv2.imshow('NATURE_PIC', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
</br>
![Screenshot 2025-03-28 111738](https://github.com/user-attachments/assets/a553a98c-9ee2-4fea-9c15-e9710f4a6cc8)

</br>


### ii) Display the video
</br>
![Screenshot 2025-03-28 111838](https://github.com/user-attachments/assets/9b3d5203-8daf-4ed4-809f-7bbdc59adf2f)

</br>


### iii) Display the video by resizing the window
</br>
![Screenshot 2025-03-28 112006](https://github.com/user-attachments/assets/a783f5ad-7105-40ea-b9b2-2b3a9c223f2a)

</br>



### iv) Rotate and display the video
</br>
![Screenshot 2025-03-28 112044](https://github.com/user-attachments/assets/08f411b5-b154-443a-979b-bfb076d6e626)

</br>

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
