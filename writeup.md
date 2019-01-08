** Finding Lane Lines on the Road**

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consists of the following steps: 
1. Converting image to grayscale and applying a Gaussian blur to the image

2. Applying Canny edge detection and Masking the image so that only the region of interest is processed.

3. Running the Hough transform to identify lines

4. Converting those lines into straight lines

5. Smoothing the result with a moving average filter

6. Plotting the lines on top of the image

In order to draw a single line on the left and right lanes, I created the function draw_straight_lines(). This function works as follows:

1. Separate the right and left line based on their slope

2. Average the line ending x,y coordinates for each side

3. Calculate the slope and intercept of each average line

4. Using the slope and intercept, extend the lines to the bottom and apex of the lane

5. Update the moving average of the last few lines and the new lines

6. Plot the moving average lines


###2. Identify potential shortcomings with your current pipeline

Not able to provide a work around for challenge video.

In low-contrast situations and at intersections with sharp angles, the line identification pipeline may not work well or the code cannot draw over the entire lane marking.

###3. Suggest possible improvements to your pipeline

One improvement would be cleaner code.
