# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I applied Gaussian smoothing and burring, followed by Canny edge detection, defining ROI and Hough transform.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by adding following steps:
1. Classify detected lines into two groups - left edges and right edges
2. Calculate an average slop for left and right edges respectively
3. Pick up one point on left edge and one point on right edge
4. Draw two lines based on the points picked in step 3 and the slops caculated in step 2 for both left and right edge

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be when the color of ground is not uniform (e.g. road color suddenly becomes lighter when the car is passing the bridge at around 00:04 in 'challenge.mp4'), the result of Canny edge detection may be impacted.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to setup an adptive thresthold strategy in Canny edge detection.
