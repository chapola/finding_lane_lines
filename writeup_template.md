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

My pipeline consisted of following steps...
1.  Applies the Grayscale transform - First I transform Image to grayscale
2.  Applies the Canny transform 
3.  Calculate the Region of interest
4. Find all the Hough lines
5. Applies the weighted method 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...
1. Interate over the lines and spreate left lines and right lines
2. Calculte the slop values using (y2-y1)/(x2-x1)
3. If slop is 0 the countinue 
4. slop > 0 Right lines
5 slop < 0  Left line
6. Then calculte left annd right mean 
7. Calculate intercept of left annd right line 
8 compute new points of lines 
9 Draw lines


If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 
1.Requires hard coded regions

Another shortcoming could be ...
2. Depands on fixed camera position


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...
1. Update the ROI mask dynamically
2.better filter to smooth the current estimation


Another potential improvement could be to ...
