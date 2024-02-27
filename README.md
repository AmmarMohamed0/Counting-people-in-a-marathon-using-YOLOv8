# Counting-people-in-a-marathon-using-YOLOv8
Imports:

- `cv2`: OpenCV library for computer vision tasks.
- `pandas`: Library for data manipulation and analysis.
- `numpy`: Library for numerical computations.
- `ultralytics.YOLO`: YOLO object detection model from the Ultralytics library.
- `Tracker`: Custom object tracker class.
- `cvzone`: Library for computer vision tasks including text rendering.

Loading YOLO Model:

An instance of the YOLO model is created using the `YOLO` class from the Ultralytics library. The YOLO model is loaded from the file `'yolov8m.pt'`.

Mouse Event Function:

A mouse event function `print_mouse_position` is defined to print the mouse position whenever the mouse is moved over the window named `'RGB'`.

Video Capture:

A video file named `"p3.mp4"` is captured using `cv2.VideoCapture()`.

Loading Class Labels:

Class labels are loaded from the file `"coco.txt"` and stored in the `class_list` variable.

Object Tracking Initialization:

An instance of the `Tracker` class is created for object tracking.

Main Loop:

- In the main loop, each frame of the video is read.
- Object detection is performed on every third frame using the YOLO model.
- Detected person coordinates are extracted and sent to the object tracker for updating.
- Bounding boxes are drawn around the detected persons, and their IDs are annotated.
- If a person crosses a predefined line (`cy1`), it is counted and marked with a red circle.
- The current count of people is displayed on the frame.
- The processed frame is displayed in a window named `'RGB'`.
- The loop continues until the user presses the 'Esc' key (27 in ASCII).

Cleanup:

Once the loop exits, the video capture is released and OpenCV windows are destroyed.
