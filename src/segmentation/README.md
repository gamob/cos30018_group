# Digit Segmentation Workflow

This workflow extracts individual digits from an image using OpenCV image processing techniques.

## Workflow Overview

```text
Input Image
    ↓
Binarization
    ↓
Noise Cleanup
    ↓
Connected Component Detection
    ↓
Wide Region Splitting
    ↓
Crop Individual Digits
    ↓
Save Digit Images
1. Image Binarization

The binarize_image() function prepares the image for segmentation.

Steps
Convert image to grayscale
Apply Gaussian blur to reduce noise
Apply Otsu thresholding
Invert image if necessary
Perform morphological cleanup
Output

Binary image:

White digits
Black background
2. Connected Component Detection

The segment_digits() function identifies separate digit regions using:

cv2.connectedComponentsWithStats()

Each connected white region is treated as a candidate digit.

Filtering

Small noisy regions are removed using:

minimum area
minimum width
minimum height
3. Wide Region Splitting

If a detected region is unusually wide, it may contain multiple touching digits.

The split_region_horizontally() function:

computes vertical projection
detects low-density gaps
splits the region into subregions

This improves segmentation for merged digits.

4. Cropping Digits

The crop_to_content() function removes extra empty space around each digit.

Result:

tighter bounding box
cleaner digit samples
easier downstream OCR/classification
5. Saving Results

For each processed image:

a folder is created in processed/
each digit is saved individually

Example:

data/
└── segmentation/
    ├── raw/
    │   └── sample.png
    └── processed/
        └── sample/
            ├── digit_1.png
            ├── digit_2.png
            └── digit_3.png
Alternative Method

The script also includes:

segment_digits_projection()

This method uses:

vertical projection analysis
gap detection between digits

It works best when digits are clearly separated horizontally.

Main Pipeline
Image
 → binarize_image()
 → segment_digits()
 → crop_to_content()
 → save digit images
