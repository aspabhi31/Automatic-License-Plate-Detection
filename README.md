# Automatic License Plate Detection (ALPD)

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python&logoColor=white)  
![OpenCV](https://img.shields.io/badge/OpenCV-4.0-green?logo=opencv&logoColor=white)  
![Tesseract OCR](https://img.shields.io/badge/Tesseract_OCR-5.0-orange)  
![Dataset](https://img.shields.io/badge/Focus-Image_Processing-red)

## Project Overview

This repository hosts the implementation and documentation for an Automatic License Plate Detection (ALPD) system. The project develops a robust image processing pipeline to detect and extract license plates from vehicle images, addressing challenges such as diverse angles, varying lighting conditions, and real-time processing needs. Applications include parking management, law enforcement, and toll collection.

The system employs techniques like grayscale conversion, Gaussian blurring, histogram equalization, adaptive thresholding, contour detection, and geometric filtering. It also incorporates OCR for text recognition and template matching for verification.

Key findings from the project:
- Effective in enhancing plate visibility under diverse conditions.
- Parameter optimization is critical for accuracy.
- Challenges remain with complex backgrounds and non-standard plates.

Current as of November 30, 2025.

## Repository Contents

- `Automatic License Plate Detection(ALPD).pdf`: Comprehensive 20-page project report including:
  - Structured abstract (introduction, methods, results, discussion, conclusions).
  - Problem statement.
  - Literature review summary (covering region-based, edge detection, morphological, and wavelet transform methods).
  - Detailed methodology.
  - Results with visualizations of blurring, equalization, thresholding, and contour detection.
  - Discussion on strengths, areas for improvement, and interesting aspects.
  - Bibliography.

- `Automatic License Plate Detection(ALPD).ipynb`: Jupyter notebook implementing the ALPD pipeline, including:
  - Image loading and display (using PIL).
  - Preprocessing (grayscale, Gaussian blur).
  - Contrast enhancement (histogram equalization).
  - Adaptive thresholding.
  - Contour detection and filtering.
  - Character segmentation and OCR (using Pytesseract).
  - Template matching (SIFT with brute-force matcher).
  - License plate format verification (regex).

## Key Methods

1. **Preprocessing**: Convert RGB to grayscale and apply Gaussian blurring (e.g., kernel sizes like (15,15)) to reduce noise while preserving edges.
2. **Contrast Enhancement**: Histogram equalization to redistribute intensity values, improving details in dark/bright areas.
3. **Adaptive Thresholding**: Segment image using local variations (e.g., block size 11, constant 4) for uneven lighting.
4. **Contour Detection**: Identify contours in binary images using OpenCV's `findContours` with external retrieval and simple approximation.
5. **Filtering and Extraction**: Filter contours based on area (>1000 pixels), shape (quadrilateral approximation), and precision (0.02 * perimeter).
6. **OCR**: Use Tesseract to recognize text from extracted regions.
7. **Template Matching**: SIFT descriptors and brute-force matching to compare with predefined templates.
8. **Verification**: Regex to check plate format (e.g., "KJX-5333").

## Dependencies

Install via pip:
```bash
pip install opencv-python pillow matplotlib pytesseract numpy
