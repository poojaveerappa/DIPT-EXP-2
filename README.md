Image Capture and Video Processing Using OpenCV
Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file
Display the video
Display the video by resizing the window
Rotate and display the video
🛠️ Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
⚙️ Algorithm
Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().


Step 2:
Capture frames continuously from the webcam.


Step 3:
Save a frame as a JPG image using cv2.imwrite().


Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

💻 Program
Developed By:
Name: POOJA V
Register No:212225040302
Output
i) Write the frame as JPG image
Captured image is saved as captured_image.jpg
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("photo.png", frame)
cap.release()
captured_image = cv2.imread('photo.png')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
<img width="645" height="505" alt="image" src="https://github.com/user-attachments/assets/c2c9197c-3b9d-4575-9b64-f05e390d6781" />

ii) Display the video
Live webcam video is displayed
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
cap.release()
```
<img width="651" height="482" alt="image" src="https://github.com/user-attachments/assets/73bd3d2a-15b0-47d6-8317-d39eef0784bc" />


iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
```
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
cap.release()
```
<img width="330" height="491" alt="image" src="https://github.com/user-attachments/assets/9b5ea8db-30a2-41c3-9996-3fafe5d81f8a" />


iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```

cap = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
cap.release()
```
<img width="386" height="482" alt="image" src="https://github.com/user-attachments/assets/2a40d709-ee37-4f26-9060-f8cf8947fc6f" />


Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
