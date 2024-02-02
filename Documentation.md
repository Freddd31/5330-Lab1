
# Sky Detector Project Documentation

## Introduction
This project aims to segment the sky in images using K-means clustering and HSV color thresholding techniques. This method effectively identifies different types of skies, such as blue skies and sunsets, and distinguishes them from other elements in the image.

## Technology Selection
### K-means Clustering
- **Principle**: K-means is a popular clustering algorithm that groups pixels based on their distance from each other.
- **Reason for Choice**: K-means clustering is suitable for color clustering issues and can effectively distinguish the sky from other scenes.

### HSV Color Thresholding
- **Principle**: HSV (Hue, Saturation, Value) is a color space ideal for color segmentation.
- **Reason for Choice**: Setting specific HSV thresholds allows for precise identification of specific color ranges, like those of blue skies or sunsets.

## Implementation Process
### Code Analysis
1. **Sky Segmentation using K-means**:
   ```python
   def segment_sky_with_kmeans(image_rgb):
       reshaped_img = image_rgb.reshape((-1, 3)).astype(np.float32)
       k = 2
       _, labels, centers = cv2.kmeans(reshaped_img, k, None, (cv2.TERM_CRITERIA_EPS + cv2.TERM_CRITERIA_MAX_ITER, 100, 0.2), 10, cv2.KMEANS_RANDOM_CENTERS)
       sky_cluster_index = np.argmax(np.mean(centers, axis=1))
       sky_mask = (labels.reshape((h, w)) == sky_cluster_index)
       return sky_mask.astype(np.uint8) * 255
   ```

2. **Applying HSV Color Thresholds**:
   ```python
   def process_image_and_display_all_steps(image_rgb):
       image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
       lower_blue = np.array([70, 50, 100])
       upper_blue = np.array([130, 255, 255])
       lower_orange_red = np.array([0, 100, 100])
       upper_orange_red = np.array([30, 255, 255])
       mask_blue = cv2.inRange(image_hsv, lower_blue, upper_blue)
       mask_orange_red = cv2.inRange(image_hsv, lower_orange_red, upper_orange_red)
       sky_mask = cv2.bitwise_or(mask_blue, mask_orange_red)
   ```

3. **Morphological Operations**:
   ```python
   kernel = np.ones((7, 7), np.uint8)
   mask_morph = cv2.morphologyEx(sky_mask, cv2.MORPH_CLOSE, kernel)
   mask_morph = cv2.morphologyEx(mask_morph, cv2.MORPH_OPEN, kernel)
   ```

4. **Setting Up Gradio Interface**:
   ```python
   demo = gr.Interface(
       fn=process_image_and_display_all_steps_gradio,
       inputs="image",
       outputs="image"
   )
   demo.launch()
   ```

## Challenges and Solutions
### Technical Challenges
- **Challenge**: How to accurately segment different types of skies.
- **Solution**: Combining K-means clustering with HSV thresholding to enhance segmentation accuracy.

### Performance Optimization
- **Challenge**: Improving the efficiency of image processing.
- **Solution**: Optimizing algorithms and code to reduce unnecessary computations.

## Conclusion
This project demonstrates how to effectively combine K-means clustering and HSV color thresholding techniques for precise sky segmentation in images. Future exploration could include more image processing techniques to further improve accuracy and efficiency.
