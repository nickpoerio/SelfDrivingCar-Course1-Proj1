# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of the following steps:

1. Conversion to grayscale: it condensates three color layers into one
2. Gaussian blur: kernel function for smoothing
3. Canny edge detection: image derivative thresholds to highlight edges
4. Mask selection: trapezoidal mask
5. Probabilistic Hough transform: line detection from masked canny edge image
6. Final output: overlay to the original image

Apart from tuning Hough and Canny transform parameters, what helped me most was appliyng a slope filter to the plotted lines, excluding horizontal lines or similar. This made the whole pipeling much more robust, less sensitive to parameters choice.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating the average of the positive and negative slopes, as well as of the related offsets.


### 2. Identify potential shortcomings with your current pipeline

The pipeline is valid for highway environment only. In this environment, the main shortcoming is related to the presence of low contrast between lines and asphalt, like in the last, optional challenge. After the second 3 or so, a very light grey asphalt and a light yellow line cause the detection to be very tricky, even adding a color selection step on the top of the pipeline: I turned asphalt to black and yellow lines to white, this worked in general, but not enough to completely solve the specific issue.
Also shadow on the road could cause difficulties to detect lines.

### 3. Suggest possible improvements to your pipeline

I probably should be keeping refining the color selection for light grey apshalt and yellow lines, or maybe improving the mask shape to a complicated non-convex polygon. This could work for the specific problems, but I hope to learn more sophisticated techniques in the next projects.
