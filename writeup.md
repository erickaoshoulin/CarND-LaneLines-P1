# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images_output/solidWhiteCurve.jpg    "solidWhiteCurve"
[image2]: ./test_images_output/solidWhiteRight.jpg    "solidWhiteRight"
[image3]: ./test_images_output/solidYellowCurve.jpg   "solidYellowCurve"
[image4]: ./test_images_output/solidYellowCurve2.jpg  "solidYellowCurve2"
[image5]: ./test_images_output/solidYellowLeft.jpg    "solidYellowLeft"
[image6]: ./test_images_output/whiteCarLaneSwitch.jpg "whiteCarLaneSwitch"
                               







---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

####My pipeline consisted of 5 steps. 
##### Step 1: converted the images to grayscale
##### Step 2: apply gaussian smoothing reduce high frequency noise 
##### Step 3: apply Canny transform to find gradient 
##### Step 4: define four sided polygon get region of interest 
##### Step 5: apply Hough transform to detect lines 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by following steps
##### Step 1: filter out unreasonable segment with too small absolute slope
##### Step 2: seperate segments into 2 groups by sign of the slopes and then average them to avg_left_slope and avg_right_slope value
##### Step 3: pick initial point with largest y1  to draw line from y=img.shape[0] to y=330. 
######ps 330 is a tuning number here.  pick largest y1 is trying to resolve the issue in challenge video, but it's does not work.



If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]
![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]
![alt text][image6]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lane is not a strait line, say, a curve in challenge video.

Another shortcoming could be that not all the camera is callibrated before mount on a car. Some magic number should be tuning like 320 in my case to filter out unessary segments.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to revise draw_line() function. 
Current pipeline we can only detect line, but we can not detect curve. We should find out some alorithm to detect curve. We should should implement curve fitting function to draw the line instead of line fitting.

Another potential improvement could be to that regions_of_interest() could be not robust enough when the camera is not calibrated before mount on the car.
