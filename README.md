# Computer-Vision- Final Project
- This project was done on a computer vision course in Udemy platform.
- The goals of the project: to recognize my hand number and show it with a counter on the Screen.

 # Generally Process:
 - First calculate changes in background.
 - Isolate the hand from the background.
 - Count fingers by points that are not inside the area of scope (include the scope).

# Stage of project:

# Stage 1- Finding Average Background Value:
- Creating the background (if background does not exist).
- This function calculates a weighted sum of the input image (`frame`) and the existing background, with the weight determined by the `accumulated_weight` parameter. This weighted sum is then used to update the background.
- That will help us to recognize if the hand comes into the ROI.

# Stage 2- Segment the Hand Region in Frame:
- Absolute Difference: The function calculates the absolute difference between the current frame and the background. This helps to highlight the regions where changes have occurred in the video stream (compare pixel by pixel).
- To recognize the contours of the hand I change the Absolute Difference to THRESH_BINARY.
- Take the largest area of contours (means the contours of hand).

# Stage 3- Counting Fingers with a Convex Hull
- Create polygon by cv.convexHull().
- Link to documentation: https://docs.opencv.org/4.x/dd/d49/tutorial_py_contour_features.html
   
    <img width="225" alt="image" src="https://github.com/IlaiGamzu/Computer-Vision-Final-Project/assets/135164356/467a5276-8a63-4fcd-b282-e04c0f75f5c0">
   
- Calculate the 4 most outward points, on the top, bottom, left, and right.
- Calculate the center point of the circle.
- Calculate the radius (the max distance between the center to the points on the scope.
- Each point outside of the circle will be counted.

# The Result:
- The numbers are recognize from 0 to 5.
- The counter display on screen.

<img width="477" alt="image" src="https://github.com/IlaiGamzu/Computer-Vision-Final-Project/assets/135164356/c7689cca-897f-451d-9aa1-e64d5d9d8ac3">

<img width="730" alt="image" src="https://github.com/IlaiGamzu/Computer-Vision-Final-Project/assets/135164356/ed92317e-a97a-4d7f-958c-6921432f8ee7">


<img width="675" alt="image" src="https://github.com/IlaiGamzu/Computer-Vision-Final-Project/assets/135164356/08782b92-c272-4d91-86a0-963b39a4cffe">

<img width="666" alt="image" src="https://github.com/IlaiGamzu/Computer-Vision-Final-Project/assets/135164356/e4163a5e-2758-4b8e-a4ac-a3f04bfc92b4">

<img width="749" alt="image" src="https://github.com/IlaiGamzu/Computer-Vision-Final-Project/assets/135164356/564daac9-01e9-451c-b2fc-39c681bf5c76">

<img width="752" alt="image" src="https://github.com/IlaiGamzu/Computer-Vision-Final-Project/assets/135164356/5924645d-3e3b-4875-b069-e70e1dd58fcb">



