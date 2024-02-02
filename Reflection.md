
# Reflection on Sky Segmentation Project

## Effectiveness of the Approach
The combination of K-means clustering and HSV color thresholding in the project significantly improved the accuracy of sky segmentation in images. Initially, without K-means, many non-sky elements were incorrectly identified as sky, affecting accuracy. Integrating K-means clustering effectively addressed this issue.

## Challenges and Solutions
### Initial Challenges
- **Non-Sky Object Detection**: Before K-means implementation, the algorithm incorrectly identified many non-sky objects as sky, leading to reduced accuracy.
- **Color Thresholding Limitations**: Initially, the algorithm struggled with recognizing skies during sunrise and sunset due to the absence of thresholds for yellowish and reddish hues.

### Additional Challenges
- **Variable Lighting Conditions**: Different lighting conditions, such as overcast or bright sunny days, presented a significant challenge in accurately detecting the sky.
- **Complex Backgrounds**: Scenarios with complex backgrounds, like urban landscapes with tall buildings, made it difficult to accurately segment the sky.

### Solutions
- **Dual Color Thresholding**: Implementing two color thresholds for different times of the day, particularly for sunrise and sunset hues, greatly enhanced accuracy.
- **Segmentation Adjustment**: Extending the segmentation from the top half to the upper two-thirds of the image improved the detection accuracy in various scenarios.
- **Adaptive Thresholding**: Modifying color thresholds based on the overall brightness of the image to handle different lighting conditions.

## Limitations and Potential Improvements
- **Incomplete Separation**: The project still struggles to completely separate the sky from all other elements, especially in complex images.
- **Color Variability**: Despite improvements, the chosen color thresholds in HSV space do not recognize all sky colors, although they are effective for most conditions.

## Learning Outcomes
- **Algorithm Integration for Precision**: The project demonstrated the effectiveness of combining different algorithms to achieve better segmentation results.
- **Adaptive Problem-Solving**: This experience highlighted the importance of adapting the approach, like changing the area of analysis, to improve accuracy.
- **Understanding Practical Limitations**: The project provided insights into the limitations of computer vision techniques, particularly in handling complex and variable natural scenes.
