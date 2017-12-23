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

My pipeline consisted of 5 steps. 
Step 1: converted the images to grayscale
Step 2: apply gaussian smoothing reduce high frequency noise 
Step 3: apply Canny transform to find gradient 
Step 4: define four sided polygon get region of interest 
Step 5: apply Hough transform to detect lines 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]
![alt text][image2]
![alt text][image3]
![alt text][image4]
![alt text][image5]
![alt text][image6]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
