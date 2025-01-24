# Arrow Detection using OpenCV

This project uses OpenCV and Python to detect arrow shapes in real-time through a webcam feed. The program processes video frames to identify contours resembling arrows and calculates the inclination of the detected arrow shapes.

## Features
- Real-time detection of arrow shapes.
- Highlights the detected arrow contours on the video feed.
- Displays the inclination angle of the detected arrow.
- Interactive interface with live video feed and mask visualization.

## Prerequisites

Ensure you have Python installed on your system. The required libraries are:

- `opencv-python`
- `numpy`

Install them using pip:
```bash
pip install opencv-python numpy
```

## How to Use
1. Clone this repository:
    ```bash
    git clone <repository_url>
    ```
2. Navigate to the project directory:
    ```bash
    cd <project_directory>
    ```
3. Run the script:
    ```bash
    python arrow_detection.py
    ```
4. The program will start the webcam feed and process frames in real-time.
   - Detected arrow shapes will be highlighted in magenta.
   - The inclination angle of the detected arrow will be printed in the console.
   - Press `q` to exit the program.

## Code Overview
- **Capture Video Feed**: The webcam feed is captured using `cv2.VideoCapture(0)`.
- **Color Masking**: The HSV color space is used to create a mask for a specific color range.
- **Contour Detection**: Contours are extracted using `cv2.findContours()`.
- **Arrow Shape Detection**:
  - Contours are approximated to polygons.
  - If a polygon with 7 vertices is detected, it is considered an arrow.
  - The centroid and inclination angle of the arrow are calculated and displayed.
- **Visualization**:
  - The mask and processed video feed are displayed in separate windows.

## Key Functions
- **cv2.cvtColor()**: Converts frames from BGR to HSV color space.
- **cv2.inRange()**: Creates a mask for the defined color range.
- **cv2.findContours()**: Detects contours from the mask.
- **cv2.approxPolyDP()**: Approximates the contours to a polygon.
- **cv2.moments()**: Calculates the centroid of a contour.
- **cv2.fitLine()**: Computes the best-fit line for the contour to calculate inclination.

## Outputs
- **Contours Window**: Shows the original frame with highlighted arrow contours.
- **Mask Window**: Displays the binary mask used for contour extraction.

## Customization
- **Color Range**: Adjust the lower (`lb`) and upper (`ub`) HSV values to detect arrows of different colors.
- **Contour Area**: Modify the area threshold (`if area > 1`) to filter out noise.

## Example
When an arrow is detected, the following outputs are shown:
- The text `"Arrow Detected"` is displayed near the detected arrow.
- The inclination angle is printed in the console.

## License
This project is open-source and available under the MIT License.

## Acknowledgments
- OpenCV documentation: https://docs.opencv.org
- Python documentation: https://docs.python.org


