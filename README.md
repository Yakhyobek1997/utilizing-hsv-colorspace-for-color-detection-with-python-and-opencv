How It Works:
Importing Libraries:

The script uses cv2 for video capture and image processing, numpy for handling arrays, and PIL for additional image manipulation.
Defining Color Limits:

The get_limits function returns the lower and upper bounds of the color in the HSV colorspace. In this example, it's set to detect yellow. You can modify this function to detect other colors by changing the HSV range.
Capturing Video:

The script initializes the webcam using cv2.VideoCapture(0). The 0 refers to the first connected camera. If your system has multiple cameras, you can change this index to use a different one.
Frame Processing:

Each frame is captured using cap.read(). The frame is then converted to the HSV colorspace using cv2.cvtColor.
A binary mask is created using cv2.inRange, which highlights the pixels that fall within the specified color range.
Bounding Box Detection:

The mask is converted to a PIL Image object, and the getbbox method is used to find the bounding box of the detected color region.
If a region matching the color is found, a green rectangle is drawn around it using cv2.rectangle.
Displaying the Output:

The processed frame is displayed in a window using cv2.imshow. The script will continue to run in a loop, updating the frame in real-time until the 'q' key is pressed.
Releasing Resources:

After exiting the loop, the script releases the camera resource using cap.release() and closes all OpenCV windows with cv2.destroyAllWindows().
