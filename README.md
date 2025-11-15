# Finger Counting with Canny Edge Detection and Geometric Analysis

This project detects the number of raised fingers in a hand image using a combination of edge detection and geometric analysis.

## Workflow

### 1. Edge Detection and Processing

**1.1 Edge Detection and Denoising**  
A Gaussian filter is applied to reduce noise, followed by Canny edge detection to extract sharp hand contours.

**1.2 Morphological Processing**  
Morphological operations (such as dilation and closing) are used to fill small gaps and smooth the edges of the hand.

**1.3 Region Filling (Mask Creation)**  
The interior of the smoothed contour is filled to create a binary mask that clearly separates the hand from the background.

**1.4 Contour Refinement**  
Edges are recalculated on the binary mask to isolate a clean, continuous outer contour of the hand.

### 2. Geometric Analysis

**2.1 Convex Hull and Defect Detection**  
The convex hull of the hand contour is computed to approximate the outer shape of the hand. Convexity defects are then analyzed to identify valleys between fingers.

**2.2 Geometric Filtering and Finger Counting**  
Invalid convexity defects are filtered out based on angle and distance thresholds. The remaining valid defects are used to estimate the number of raised fingers, with additional logic for special cases such as a closed fist or a single raised finger.

## Requirements

- Python 3  
- NumPy  
- OpenCV  
- scikit-image  
- SciPy  
- Matplotlib  
- pyautogui (if used for capturing or automation)

Install (example):

```bash
pip install numpy opencv-python scikit-image scipy matplotlib pyautogui
