# Automatic Number Plate Recognition (ANPR) Project

This repository contains an Automatic Number Plate Recognition (ANPR) system that detects and reads license plates from video files. The project uses OpenCV for image processing, EasyOCR for text recognition, and Python for implementation.

## Features
- Detects license plates in video frames.
- Reads and extracts text from the detected license plates using OCR.
- Outputs a processed video with detected license plates highlighted and their numbers displayed.

## Prerequisites

Ensure you have the following installed:
- Python 3.7 or higher
- OpenCV
- EasyOCR
- NumPy
- imutils
- Matplotlib

## Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/anpr-project.git
   cd anpr-project
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Place the test images and videos in the `images/` and `videos/` directories, respectively.

4. Run the code:
   ```bash
   python plate_no_detection.py
   ```

## File Structure
```
ANPR-Project/
├── images/
│   ├── test_image1.jpg
│   ├── test_image2.jpg
│   └── ...
├── videos/
│   ├── tc.mp4         # Input video
│   ├── detected_video2.mp4  # Processed output video
├── plate_no_detection.py
├── requirements.txt
├── README.md
└── plate_no_detection.ipynb
```

## Code Explanation

The main functionality is implemented in `plate_no_detection.py`. Below is a brief explanation of the process:

### 1. **Image Preprocessing**
- Convert the input frame to grayscale.
- Apply bilateral filtering to reduce noise.
- Use Canny edge detection to identify edges.

### 2. **Contour Detection**
- Find contours in the edged image.
- Sort and select the top 10 largest contours.
- Approximate the contours to identify quadrilateral shapes (potential license plates).

### 3. **Text Recognition**
- Extract the region of interest (ROI) corresponding to the detected license plate.
- Use EasyOCR to read the text from the ROI.

### 4. **Visualization**
- Overlay the detected license plate text and bounding box on the original video frame.

### 5. **Video Processing**
- Process each frame of the input video.
- Save the processed frames into an output video file.

## Example Output

### Input Video
Original input video (`videos/tc.mp4`) is processed to detect license plates.

### Output Video
Processed video (`videos/detected_video.mp4`) highlights license plates and overlays the detected text.

### Test Images
Results of detection on test images:
- ![Test Image 1](images/test_image1.jpg)
- ![Test Image 2](images/test_image2.jpg)

### Output Video Snapshot
Snapshots of processed video frames:
- ![Frame 1](images/frame1.jpg)
- ![Frame 2](images/frame2.jpg)

## Acknowledgments
This project utilizes:
- [OpenCV](https://opencv.org/)
- [EasyOCR](https://github.com/JaidedAI/EasyOCR)
- [imutils](https://github.com/jrosebr1/imutils)

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.
