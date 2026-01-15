# Homography-Based Detection Transfer

This repository presents an applied computer vision experiment focused on transferring
object detections between images or video frames that share an overlapping field of view.

The approach is based on planar homography estimation and is suitable for multi-view
camera setups, rotating cameras, and panoramic video analysis.

---

## Project Overview

In many computer vision systems, object detection is performed independently
for each camera view. However, when two views observe the same planar scene region,
detections from one view can be geometrically projected onto another.

This repository implements a complete detection transfer pipeline that:
- performs object detection on a reference frame,
- estimates a homography matrix between views,
- projects bounding boxes to a target frame,
- normalizes projected coordinates,
- visualizes and optionally saves the results.

---

## Core Concepts

- Planar homography and projective geometry
- Feature-based image alignment using SIFT and RANSAC
- Cross-view object detection transfer
- Geometric consistency across camera viewpoints

---

## Pipeline Description

1. Load two images or video frames with an overlapping field of view  
2. Detect objects on the reference frame using YOLOv8  
3. Extract SIFT keypoints and descriptors  
4. Estimate the homography matrix between the frames  
5. Project bounding box coordinates using homography  
6. Normalize projected bounding boxes  
7. Visualize the transferred detections  

---

## Technologies Used

- Python  
- OpenCV (SIFT, homography, image processing)  
- Ultralytics YOLOv8  
- Supervision (visualization and annotation)  
- NumPy, Matplotlib  
- Jupyter Notebook / Google Colab  

---

## Repository Structure

- `notebooks/` — main research notebooks  
- `README.md` — project overview

---

## Use Cases

- Multi-camera object tracking  
- Camera calibration validation  
- Cross-view object localization  
- Video analytics with rotating or moving cameras  
- Research and education in geometric computer vision  

---

## Notes and Limitations

- The method assumes a mostly planar scene  
- Accurate homography estimation requires sufficient visual overlap  
- Strong non-planar geometry may reduce projection accuracy  

---

## Status

The project is complete and demonstrates a research-grade pipeline
for homography-based detection transfer. The solution can be extended
to full video pipelines and multi-camera tracking systems.
