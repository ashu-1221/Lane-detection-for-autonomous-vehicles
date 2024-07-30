# Lane-detection-for-autonomous-vehicles


This project implements a lane detection system for autonomous vehicles using computer vision techniques. It takes video as input data, process it and highlight lane markings, aiding in lane-keeping for autonomous driving.

## Project Overview

The project is divided into two main components:
1. **Lane Detection**: Processes video frames to detect and visualize lane markings.
2. **Image Preprocessing and PSNR Calculation**: Handles image preprocessing and evaluates the quality of image reconstruction using PSNR (Peak Signal-to-Noise Ratio).

## Libraries 

libraries Used:-

- `opencv-python`
- `numpy`
- `Pillow`
- `tensorflow`

##Lane Detection


This component processes video frames to detect and highlight lane markings. The following steps are involved:

1. **Prepare the Video File**:
   - Place a video file named `test2.mp4` in the working directory. This video will be processed for lane detection.

2. **Run the Lane Detection Script**:
   - Save the lane detection code in a file named `lane_detection.py`.
   - Execute the script using:

     ```bash
     python lane_detection.py
     ```

   - The script will process the video frames and display the lane detection results. Press `q` to exit the video playback.

#### Code Details

- **`make_coordinates`**: Converts line parameters (slope and intercept) into coordinates for drawing lines on the image.
- **`average_slope_intercept`**: Averages the slope and intercept of detected lines to compute the final lane lines.
- **`canny`**: Applies Canny edge detection to the image to find edges.
- **`display_lines`**: Draws detected lane lines on the image.
- **`region_of_interest`**: Masks out non-relevant areas of the image to focus on lane detection.
- **Main Loop**: Processes video frames, detects lane markings, and visualizes the results.

## Image Preprocessing and PSNR Calculation

This component handles the preprocessing of images and evaluates the quality of image reconstruction using Peak Signal-to-Noise Ratio (PSNR). The following steps are involved:

1. **Prepare the Dataset**:
   - Ensure you have a directory with grayscale images located at `D:\Lane detection\Output result`.

2. **Trained Autoencoder Model**:
   - Ensure you have a trained autoencoder model saved as `autoencoder.h5`.

3. **Run the Preprocessing and PSNR Calculation Script**:
   - Save the preprocessing and PSNR calculation code in a file named `psnr_calculation.py`.
   - Execute the script using:

     ```bash
     python psnr_calculation.py
     ```

   - The script will preprocess the images, perform image reconstruction using the autoencoder, and calculate the PSNR for each reconstructed image. The average PSNR value will be printed to the console.

#### Code Details

- **Preprocessing**: Converts images to grayscale, resizes them to 28x28 pixels, and normalizes pixel values.
- **`psnr`**: Calculates the Peak Signal-to-Noise Ratio between the original and reconstructed images.
- **Model Loading and Evaluation**: Loads the trained autoencoder model, reconstructs images, and calculates the PSNR values.


## Code Overview

### Lane Detection (`lane_detection.py`)

- **`make_coordinates`**: Converts line parameters (slope and intercept) into coordinates for drawing lines on the image.
- **`average_slope_intercept`**: Averages the slope and intercept of detected lines to compute the final lane lines.
- **`canny`**: Applies Canny edge detection to the image to find edges.
- **`display_lines`**: Draws detected lane lines on the image.
- **`region_of_interest`**: Masks out non-relevant areas of the image to focus on lane detection.
- **Main Loop**: Processes video frames to detect and visualize lane markings.

### Image Preprocessing and PSNR Calculation (`psnr_calculation.py`)

- **Preprocessing**: Converts images to grayscale, resizes them to 28x28 pixels, and normalizes pixel values.
- **`psnr`**: Computes the Peak Signal-to-Noise Ratio between true images and their reconstructed versions.
- **Model Loading and Evaluation**: Loads a pre-trained autoencoder model, reconstructs images, and calculates PSNR values.









