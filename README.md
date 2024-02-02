# 5330-Lab1: Sky Detector in Images

## Introduction
This project utilizes K-means clustering and color thresholding methods to segment the sky areas in images. By combining these two techniques, we are able to efficiently identify and process different types of skies, such as blue skies and sunsets. This application is suitable for sky segmentation and replacement in natural landscape photography.

## Features
- Identifies sky regions using the K-means clustering algorithm.
- Refines sky regions using color thresholds in the HSV color space.
- Merges and processes images with various types of skies (blue sky and sunset).
- Improves sky masks using morphological operations.
- Replaces sky regions with a plain white color, suitable for further image processing or enhancement.

## Installation
To use this project, please install the following dependencies:

```bash
pip install gradio cv2 numpy matplotlib scikit-learn Pillow
```

## Usage Instructions
The project includes a Gradio interface for uploading images and displaying the various steps of the processing. To launch the interface, run the following code:

```python
demo.launch()
```

## Example
- Run the program.
- Upload an image with sky through the Gradio interface.
- View and analyze the processed results, including the K-means sky mask, blue sky mask, sunset sky mask, morphologically processed mask, and the final image with white sky.



