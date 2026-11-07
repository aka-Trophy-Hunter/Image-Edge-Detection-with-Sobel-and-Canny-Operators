# Image Edge Detection with Sobel and Canny Operators

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Image%20Processing-5C3EE8?logo=opencv&logoColor=white)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-F37626?logo=jupyter&logoColor=white)

## Overview

This project explores two classical edge detection techniques, the **Sobel operator** and the **Canny edge detector**. Both are implemented in Python and applied to the same input image, which shows how image gradients can be used to find boundaries, structures and intensity changes.

The implementation uses **OpenCV** for image processing and **Matplotlib** for side-by-side visual comparison.

## Tech Stack

| Tool | Purpose |
|---|---|
| **Python** | Core programming language |
| **OpenCV** | Image processing and edge detection |
| **NumPy** | Numerical operations and image array manipulation |
| **Matplotlib** | Displaying and comparing results |

## Project Structure

```text
.
├── sobel_canny_edge_detection.ipynb   # Main notebook
├── image.png                          # Input image (add your own)
└── README.md
```

## Getting Started

### 1. Clone the repository

```bash
git clone (https://github.com/aka-Trophy-Hunter/Image-Edge-Detection-with-Sobel-and-Canny-Operators)
cd Image-Edge-Detection-with-Sobel-and-Canny-Operators
```

### 2. Install dependencies

```bash
pip install opencv-python numpy matplotlib
```

### 3. Add an input image

Place an image named `image.png` in the project directory.

### 4. Run the notebook

Open `sobel_canny_edge_detection.ipynb` in Jupyter Notebook or JupyterLab and run all cells.

## Edge Detection Methods

### 1. Sobel Operator

The Sobel operator estimates how quickly pixel intensity changes by convolving the image with two 3×3 kernels, one for each direction:

```text
Gx = [-1  0  1]      Gy = [-1 -2 -1]
     [-2  0  2]           [ 0  0  0]
     [-1  0  1]           [ 1  2  1]
```

The two gradients are combined into a single edge strength map:

```text
magnitude = sqrt(Gx² + Gy²)
```

Strong responses mark prominent edges. Weak responses mark flat regions.

### 2. Canny Edge Detector

Canny is a multi-stage algorithm that produces thin, clean edges:

1. **Gaussian filtering** reduces noise.
2. **Gradient computation** finds candidate edges.
3. **Non-maximum suppression** thins edges to single-pixel width.
4. **Double thresholding** separates strong edges, weak edges and non-edges.
5. **Edge tracking by hysteresis** keeps weak edges only if they connect to strong ones.

## Results

The notebook displays three images side by side:

| Output | Description |
|---|---|
| **Original image** | The input before processing |
| **Sobel output** | Edges from horizontal and vertical gradient calculations |
| **Canny output** | Refined edge boundaries from the multi-stage algorithm |


![Edge detection comparison](detection%20result.png)

## Sobel vs. Canny

| | Sobel | Canny |
|---|---|---|
| **Approach** | Gradient magnitude from convolution kernels | Multi-stage pipeline built on gradients |
| **Edge thickness** | Often thick | Thin (single pixel) |
| **Noise handling** | Sensitive unless the image is pre-smoothed | Smoothing built in (Gaussian filter) |
| **Parameters** | Kernel size | Two thresholds (plus smoothing strength) |
| **Complexity** | Simple and fast | More steps, cleaner results |

## Project Objectives

- Understand the fundamentals of edge detection in computer vision
- Explore gradient-based image processing with the Sobel operator
- Implement and examine the Canny edge detection algorithm
- Compare the outputs of the two techniques

## Acknowledgments

This project uses [OpenCV](https://opencv.org/) for image processing and [Matplotlib](https://matplotlib.org/) for visualization.
