#**Finding Lane Lines on the Road** 

##Writeup Template

###You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I defined a kernel and applied a gaussian brur filter on the image. I did a canny transformation and created a masked edges image. Use the Houg Transormation to find the lines. This lines are then extrapolated and connected using a modified draw_lines(). The final original image is returned with lines in red overlapping the white or yellow lines in the images/video. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by identifying the end point and the slope, then the function draw a new line usign a linear regression on the end points provided. I have taken inspiration from the projected I forked in my repository from a past student that developed a new draw_lines function that I think was brilliant. I have adapted her functions here. I would like to cite her here because her work contributed to my submission and my learning togheter with the forum and several other commits from other students. Please see my fork to her repo. ( cite  http://www.jessicayung.com/ or https://hk.linkedin.com/in/jessicayungyc or https://github.com/jessicayung )


###2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be what would happen when when there are no lines on the road, or when the lines are multiples and the road change while you driving. Also, we should calibrate the function to better identify lines on more difficult roads.


###3. Suggest possible improvements to your pipeline

A possible improvement would be to write a calibration function to improve the line detection.
