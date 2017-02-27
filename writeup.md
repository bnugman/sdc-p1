**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of the following steps:
- grayscale conversion
- gaussian blur with kernel value of 5
- canny edge detection with threshold values of 60 and 255
- masking a region of interest
- extracting lines using hough transform

In order to draw a single line on the left and right lanes, I modified the draw_lines() by calling improve_lines() that does the following:
 
- separate the lines by slope sign
- only retain the longest line for each slope sign
- extend the lines to the entire lower portion of the image 

If you'd like to include images to show how the pipeline works, here is how to include an image: 

[img1]: ./test_images/out.solidWhiteCurve.jpg


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lane lines are not oriented as expected, e.g., with curved lines, or perhaps when a vehicle is not positioned along the lane lines.

Another shortcoming could be appearance of prounced straigh lines in the picture, like rails, wall markings, etc that can be confused with the lane markings.


###3. Suggest possible improvements to your pipeline

A possible improvement would be to only look for lane lines using the color of the pavement that is known to be correct. That would prevent the detection of lines outside of the pavement.

Another potential improvement for a video feed would be to take advantage of continuity of the image.