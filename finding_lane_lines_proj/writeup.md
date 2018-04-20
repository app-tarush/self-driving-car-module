# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 7 steps. First, I made a copy of image, then converted the copied image to grayscale, then I used canny algorithm to find edges and also used gaussian_blur, then I selected the region, then used hough trasform to find lines and drawn various lines into image and finally I calculated weighted image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first calculated slope & center for every line then check if slope is < 0 then `slope, center` belongs to left line and if slope is > 0 then `slope, center` belongs to right line. Next I calculated the average of right and left line slopes & centres then find the x1, y1, x2, y2 using equation as (y - yc) = m(x - xc) and finally using `cv2.line()` drawn a single line.  

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when region of interest gets changed, this is not automatic.

Another shortcoming could be running on centre of the lanes.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...