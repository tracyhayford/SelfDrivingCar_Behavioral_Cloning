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

My pipeline consisted of 5 steps. First, I converted the images to grayscale (grayscale helper), then I performed a slight blurring (gaussian_blur helper) of the image followed by edge detection (canny helper).  Next, the an image mask is calculated and applied (region_of_interest helper) to limit processing to the image area expected to contain the lanes.  The hough_line helper was used to detect the lane markers in the processed image and create a new image with the lanes detected.  This image is overlayed onto the original image (weighted_img helper).  Finish by displaying the result and creating a file with that result.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by classifying each line as either left or right (based on it's slope) and then averaged the slopes and the center point of the line to draw a single line for the right line marker and a second single line for the left lane marker.  Lines that are nearly horizontal or nearly vertical are ignored.



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when images of different sizes are used the lane lines are not adapted to the different image size.

Another shortcoming could be the possibility of detecting the edge of approaching vehicles as lane lines.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to add more error checking and provide the necessary code to adapt to different image sizes.

Another potential improvement could be to add flexibility to the helpers by including additional parameters for adjustments to the processing.
