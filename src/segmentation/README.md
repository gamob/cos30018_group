2. Image Segmentation (Task 2)

Think of this as the "scissors"! If a user uploads a picture of a full number like "26", this part cuts it into individual pieces.  

Localization: Finding exactly where the ink is on the page.  

Partitioning: Separating a multi-digit image into sub-images, where each sub-image contains just one single digit.  

Preparation: Passing those tiny individual digit squares over to the ML model.

What to do: Write code that detects "blobs" of ink in an image and draws a box around them. You need to investigate 2 techniques (e.g., Contour detection using OpenCV vs. Bounding Boxes).   
What to use to test: Create an image with a multi-digit number (like "456") and see if your code can save three separate images: "4", "5", and "6".   
The Goal: Correct separation. If the numbers are touching, can your code handle it?
Success Metric: "1 total image in -> X separate digit images out."
