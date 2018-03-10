# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of the following steps:

1. conversion to grayscale
2. Gaussian blur
3. Canny edge detection
4. Mask selection
5. Probabilistic Hough transform
6. Final output

Apart from tuning Hough and Canny transform parameters, what helped me most was appliyng a slope filter to the plotted lines. This made the whole pipeling much more robust, less sensitive to parameters

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating the average of the positive and negative slopes, as well as of the related offsets.


### 2. Identify potential shortcomings with your current pipeline

The pipeline is valid for highway environment only. In this environment, the main shortcoming is related to the presence of low contrast between lines and asphalt, like in the last, optional channel. After second 3 or so, a very light grey asphalt and a light yellow line cause the detection very difficult, even adding a color selection on the top of the pipeline


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
