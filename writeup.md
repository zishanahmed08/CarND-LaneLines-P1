# **Finding Lane Lines on the Road** 

[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

This projects adheres to the rubric requirements

My pipeline is as below
-Read the image  and converted to grayscale (1 dimensional image)
-Removed noise with Gaussian smoothing of appropriate kernel size
-Defined the parameters for Canny edge detector and applied to get edges of an image
-Masked edges image using cv2.fillPoly() (inorder to ignore everything outside region of interest)
-Defined Hough transform parameters and ran Hough transform on masked edge-detected image
-Drew lines extrapolated from line segments .We  know that the slope = tan (theta)
Theta(Angle with x axis) of the left lane is less than 90 degree, so slope will be a positive value .Also accepted lines with slope only between degrees 25 and 40
Theta of the right lane is greater than 90 degree, so slope will be a negative value 
-Averaged the line segments
-Combined line image with original image to see how accurate the line segments were
-Tested  the video to see if the lanes are detected

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be the challenge video in which the lanes are not detected and in the solidyellow video the outliers could be seen after a few seconds

### 3. Suggest possible improvements to your pipeline

A possible improvement would be using of past frames and taking mean of all inorder to get smooth lines and another improvement would be normalization which helps in  removing highlighted regions, shadows and make that object easier to detect.So to reduce the effects of light, Normalization of color space is helpful


