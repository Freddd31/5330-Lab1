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
1.The project includes a Gradio interface for uploading images and displaying the various steps of the processing. To launch the interface in the local Gradio, run the following code:

    ```python
    demo = gr.Interface(
    fn=process_image_and_display_all_steps_gradio,
    inputs="image",
    outputs="image"
    )
    demo.launch()
    ```
2. Accessing the Deployed Application:
    To run the application on the deployed website through Hugging Face Spaces, follow these steps:
    1. First, ensure Git LFS (Large File Storage) is installed on your system. If not, install it using the following command:
   
        '''git lfs install'''
    2. Clone the repository from Hugging Face Spaces:
    
        '''git clone https://huggingface.co/spaces/Fredrickkk/Sky-Detector'''
        
    3. After cloning, navigate to the cloned directory and execute the application as per the provided instructions in the repository.    


## Example
- Run the program.
- Upload an image with sky through the Gradio interface.
- View and analyze the processed results, including the K-means sky mask, blue sky mask, sunset sky mask, morphologically processed mask, and the final image with white sky.


## Accessing Sky Detector on Hugging Face

Sky Detector is hosted on Hugging Face Spaces, providing an easy and interactive way to use the application. To access it, follow these simple steps:

1. **Visit the Application**: Open your web browser and go to [Sky Detector on Hugging Face](https://huggingface.co/spaces/Fredrickkk/Sky-Detector).

2. **Upload Your Image**: Once you are on the Sky Detector page, you can upload an image of the sky that you want to analyze. Look for the upload button or drag-and-drop area to add your image.

3. **Analyze the Sky**: After uploading your image, the application will automatically process it. Wait for a few moments for the analysis to complete.

4. **View Results**: Once the analysis is done, you'll see the results displayed on the screen, with original picture on the left, and the final image with white sky.

5. **Interact and Experiment**: Feel free to upload different images and explore the capabilities of Sky Detector.

