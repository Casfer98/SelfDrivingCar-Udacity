# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images/solidWhiteCurve.jpg "Original Image"
[image2]: ./output_images/grayscale.png "Grayscale"
[image3]: ./output_images/gaussianblur.png "Gaussian Blur"
[image4]: ./output_images/canny.png "Canny edge"
[image5]: ./output_images/region.png "Region of interest"
[image6]: ./output_images/hough.png "Hough lines"
[image7]: ./output_images/final.png "Final image"

---

### Reflection

### 1. Pipeline description.

My pipeline consisted of 5 steps. 
First, I load the image.
![alt text][image1]

Convert to grayscale.
![alt text][image2]

Apply gaussian blur to a grayscale image.
![alt text][image3]

Apply canny edge to a gaussian blur image.
![alt text][image4]

Define region of interest in the image.
![alt text][image5]

Apply hough lines to find all the lines.
![alt text][image6]

Weighted final image
![alt text][image7]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by:
Get the mid point of all lines detected.
Determines whether the midpoint is loaded on the right or left side of the image and classifies it.
Use a simple linear regression to get m and b parameters the midpoint of left and right lines detected.
Define the x1, y1 and x2, y2 points to draw the left and right line to cover the region of interest x = (y - b) / m.
Draw the left and right lane lines.

### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the road is damaged by a hole or potholes.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be add color detection to the code.
