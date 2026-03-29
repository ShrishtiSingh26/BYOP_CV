# Image Stitching using Computer Vision (BYOP Project)

## Overview

This project implements an **image stitching pipeline** that combines multiple overlapping images into a single panoramic image. It demonstrates core **computer vision concepts** such as feature detection, feature matching, homography estimation, and image warping.

The goal of this project is to solve a real-world problem:

> *Creating wide-angle panoramic images without requiring specialized hardware.*

---

## Problem Statement

Capturing large scenes (landscapes, buildings, events) often requires wide-angle lenses or multiple shots. However:

* Wide-angle lenses are expensive
* Single images cannot cover large fields of view

This project addresses this by:
Automatically stitching multiple images into one seamless panorama.

---

## Solution Approach

The pipeline follows these steps:

1. **Image Input**

   * Multiple overlapping images are provided

2. **Feature Detection**

   * ORB (Oriented FAST and Rotated BRIEF) is used to detect keypoints

3. **Feature Matching**

   * Brute Force Matcher (Hamming distance) is used

4. **Homography Estimation**

   * RANSAC is used to compute transformation between images

5. **Image Warping**

   * Images are aligned using perspective transformation

6. **Blending**

   * Overlapping regions are merged to form a stitched image

---

## Project Structure

```
BYOP_CV/
│
├── stitch.py              # Main stitching pipeline
├── matchers.py           # Feature detection and matching
│
├── images/               # Input images
│   ├── 1.jpg
│   ├── 2.jpg
│   ├── 3.jpg
│
├── txtlists/
│   └── files1.txt        # Image paths
│
└── test12.jpg            # Output panorama
```

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```
git clone <your-repo-link>
cd BYOP_CV
```

### 2. Install Dependencies

```
pip install opencv-python numpy
```

---

##  How to Run

### Step 1: Add Images

* Place your images inside the `images/` folder
* Ensure images have **overlap (30–60%)**

---

### Step 2: Update Image List

Edit:

```
txtlists/files1.txt
```

Example:

```
images/1.jpg
images/2.jpg
images/3.jpg
```

---

### Step 3: Run the Program

```
python stitch.py
```

---

### Output

* Final stitched image will be saved as:

```
test12.jpg
test1.jpg
```

![alt text](<Screenshot 2026-03-29 094656.png>) ![alt text](<Screenshot 2026-03-29 094514.png>)
---

##  Example Use Cases

* Panorama creation (landscape photography)
* Surveillance stitching
* Medical imaging (scan merging)
* Satellite image stitching

---

##  Limitations

* Requires overlapping images
* No advanced blending → visible seams may appear
* Sensitive to lighting differences
* Performance is slow due to pixel-wise merging

---

##  Future Improvements

* Seamless blending (feathering / multi-band blending)
* Cylindrical or spherical projection
* Automatic image ordering
* GPU acceleration
* Deep learning-based feature matching

---

##  Concepts Used

* Feature Detection (ORB)
* Feature Matching
* Homography & RANSAC
* Perspective Transformation
* Image Processing (OpenCV)

---

##  Learning Outcomes

Through this project, I learned:

* How real-world computer vision pipelines are built
* Practical challenges in feature matching and alignment
* Importance of robust estimation (RANSAC)
* Trade-offs between classical CV methods and modern approaches

---

##  Conclusion

This project demonstrates how fundamental computer vision techniques can be applied to solve a real-world problem effectively. While simple in implementation, it provides strong insight into image alignment, transformation, and stitching pipelines used in real applications.

---

##  Acknowledgment

This project was developed as part of the **Bring Your Own Project (BYOP)** initiative, focusing on applying theoretical knowledge to solve practical problems.

---
