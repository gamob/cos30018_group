1. Image Preprocessing (Task 1)

This is the "clean-up crew"! Raw images from the real world are usually messy, so this module prepares them for the AI.

Grayscaling: Converting colored images into black and white (or shades of gray) to simplify the data.

Resizing: Making sure every image is the exact same pixel size (like $28 \times 28$ for MNIST) so the ML model doesn't get confused.

Binarization (Optional): Turning the image into pure black and white (0s and 1s) to make the digits pop.  

What to do: Create functions that take a "dirty" raw image and turn it into a standardized format (like a $28 \times 28$ grayscale array). You need to investigate at least 2 different techniques (e.g., simple thresholding vs. Gaussian blurring).   
What to use to test: Use a few random photos of handwritten numbers taken with a phone camera.
The Goal: Ensure the output is always the exact same size and format so the ML model doesn't "break."   
Success Metric: Does the output look like a clean, centered version of the input?
