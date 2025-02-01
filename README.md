# Object-Counting-and-Tracking

## Overview

This project demonstrates how to count and track unique defects (e.g. dents and scratches) in a video using a custom-trained YOLOv8 model, Supervision, and ByteTrack. The system processes a video file, annotates each frame with detected objects and their unique tracker IDs, and finally produces both an annotated output video and a summary CSV file containing overall defect counts.

## Features

- **Custom YOLOv8 Model**: Leverage a custom-trained model to detect specific defect classes (e.g. dent and scratch).
- **Object Tracking with ByteTrack**: Maintains unique tracker IDs across video frames to ensure each defect is counted only once.
- **Video Annotation**: Annotates video frames with bounding boxes, class names, and tracker IDs for visual validation.
- **Summary CSV Report**: Aggregates overall counts of unique defects over the whole video and saves the result as a CSV file.
- **Easy Integration**: Built with Python, utilizing the Supervision library for streamlined video processing and annotation.

## Conda Env Setup

To create a reproducible environment with Conda, follow these steps:

1. **Create the Conda Environment**  
   Open your terminal and run:
   ```bash
   conda create --name defect-tracker python=3.9
   conda activate defect-tracker
   ```

2. **Install Dependencies**  
   Install the required libraries using `pip`:
   ```bash
   pip install ultralytics==8.3.19 supervision[assets]==0.24.0 opencv-python-headless numpy
   ```

   *Note:* Adjust the version numbers as needed.

3. **Optional: Save the Environment**  
   You can export the environment to a YAML file for sharing:
   ```bash
   conda env export > environment.yml
   ```

## Usage

1. **Prepare Your Files**  
   - Place your input video (e.g., `video.mp4`) in an appropriate directory (e.g., `input/`).
   - Ensure your custom YOLOv8 weight file (e.g., `best.py`) is available in the `model/` folder.

2. **Run the Script**  
   Execute the Python script to process the video:
   ```bash
   python track_defects.py
   ```
   The script will:
   - Process each frame from the input video.
   - Annotate frames with bounding boxes, labels, and tracker IDs.
   - Save an annotated video as `results.mp4` in the current working directory.
   - Generate a summary CSV file (`tracking_summary.csv`) that includes the overall unique count of defects per class.

3. **View Results**  
   - Open `results.mp4` to review the annotated video.
   - Check `tracking_summary.csv` for a summary of detected defects.

## License

This project is licensed under the MIT License.
