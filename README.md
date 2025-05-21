# 🚦 Traffic Signal Violation Detection System

This project implements an intelligent system to automatically detect **traffic signal violations** using a combination of computer vision and deep learning. It detects vehicles that cross an intersection during a **red light**, tracks their movement, and logs violations with essential details like frame number, vehicle ID, and license plate.

---

## 📂 Table of Contents

- [Features](#features)
- [System Workflow](#system-workflow)
- [Require Files](#require-files)
- [Installation](#installation)
- [Model Details](#model-details)
- [Dependencies](#dependencies)
---

## ✅ Features

- Detects vehicles using YOLOv8
- Tracks vehicles across frames using SORT
- Detects red-light signal status using histogram-based image comparison
- Identifies and logs vehicles that violate red-light rules
- Saves annotated videos with violation indicators
- Extracts license plate info (if integrated with an OCR or external service)
- Saves a CSV file containing violation records

---

---
## 🧠 System Workflow
1. Load and preprocess video frame-by-frame
2. Use YOLOv8 for vehicle detection
3. Apply SORT to track each vehicle with unique IDs
4. Compare grayscale histograms to detect red/green signal using reference images
5. When red signal is detected:
   - Check vehicle positions for violation zone
   - Log vehicle ID, bounding box, frame number
   - Extract and save license plate crop
6. Save annotated video and violation logs

---
## Required Files
1. Input vioation video (.mp4)
2. YOLOv8 model (.pt)
3. sort file (.py)
4. Traffic signal histogram (.pkl)
5. CSV file containing vioation data (.csv)
---

## ⚙️ Installation

### 1. Clone the sort repository
!git clone https://github.com/abewley/sort

%cd /content/sort
#### 2. Install the dependencies
!pip install ultralytics

!pip install -r requirements.txt

!pip install filterpy

#### 3. Change Matplotlib backend to Agg
In sort.py file change matplotlib.use('TkAgg') to matplotlib.use('Agg')

---

---
## 📊 Model Details
1. YOLOv8:

- Used for real-time object detection.

- Custom-trained model can be used to detect specific vehicle types.

2. SORT:

- Lightweight tracking algorithm.

- Assigns consistent IDs across frames.

3. Red Signal Detection:

- Uses grayscale histogram comparison between current frame and reference red/green light images.

## 🧩 Dependencies
- Python 3.8+

- OpenCV

-  NumPy

- Ultralytics YOLO

- matplotlib

- sort-tracker
