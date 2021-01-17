# **Finding Lane Lines on the Road** 

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. My Pipeline

**My pipeline consists of 6 steps.**
1. Convert images to grayscale
2. Apply gaussian blur
3. Apply canny
4. Define a region of interest which varies with the size of image
5. Apply hough transform with modified ***draw_lines()*** function 
6. Add weight to the image

**Methodology of ***draw_lines()*** function**
The goal is to find and draw only two lines: left and right lanes.
1. Classify all lines to either left or right lanes, by putting a condition: slope either greater than 0.5 or smaller than -0.5. The rest of the lines are discarded.
2. Take average on the coordinates of two groups of lines respectively to obtain two presumedly perfect lines.
3. Intepolate two lines to roughly the middle and the bottom of the image which are to annotate left and right lanes.

### 2. Potential Shortcomings

**Lane lines deviate vigorously in Challenge video**
Due to the shadow, tyre marks, and a greater curvature of lanes, perfect straight lane lines are harder to find in Challenge video.

### 3. Suggested Improvements

To improve the above shortcomings in Challeng video, lane line coordinates from last image should be taken in consideration as a reference for finding next lane line. Some kind of moving average filter may apply.