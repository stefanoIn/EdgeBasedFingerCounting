# Finger Counting Using Convexity Defects

This project detects how many fingers are raised in a hand image using classical computer vision techniques. The method does not use machine learning: instead, it relies on contour extraction, convex hull computation, and convexity defects to identify the gaps between fingers.

## Method Overview

1. **Preprocessing**  
   Grayscale conversion and Gaussian smoothing to reduce noise.

2. **Edge Detection**  
   Canny edge detection is applied to obtain the hand's outline.

3. **Contour Extraction**  
   The largest external contour is selected as the hand.

4. **Convex Hull & Defects**  
   The convex hull is computed, and convexity defects are used to detect the valleys between fingers.

5. **Finger Counting**  
   Each valid convexity defect corresponds to a separation between two fingers:  
   **fingers = defects + 1**

## Requirements

- Python 3  
- OpenCV  
- NumPy  
- Matplotlib (optional for visualization)

Install:

```bash
pip install opencv-python numpy matplotlib
