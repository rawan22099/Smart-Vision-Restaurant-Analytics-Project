[![Supported By SDAIA Academy](https://img.shields.io/badge/Supported%20By-SDAIA%20Academy-007A3D?style=for-the-badge&logo=github)](https://github.com/SDAIAAcademy)

# Smart Vision Restaurant Analytics Project

## Project Description

This project is a computer vision video analytics system designed to analyze a restaurant environment using a video input.

The project uses YOLO-based person detection and tracking together with OpenCV to analyze different areas and activities in the video. It implements five main computer vision tasks: queue counting, employee area tracking, table occupancy detection, crowd congestion and heatmap visualization, and face blurring.

The project is implemented using Python and Google Colab, with the input video loaded from Google Drive.

---

## Project Tasks

### 1. Queue Counting

The system detects people in the video using YOLO and defines a specific Region of Interest (ROI) for the queue area.

People whose detected foot point falls inside the queue ROI are counted, and the current queue count is displayed on the video.

The system also draws the queue region and bounding boxes around detected people.

---

### 2. Staff Area Tracking

The system tracks people inside a defined employee/staff area.

YOLO tracking is used with the **ByteTrack** tracker to assign tracking IDs to detected people.

When a tracked person is inside the defined staff ROI, the system displays an employee ID next to the detected person.

---

### 3. Table Occupancy Detection

The project defines specific polygonal regions representing restaurant tables.

The system detects people and checks whether their foot points fall inside each table region.

Each table is then classified as:

* **Occupied**
* **Available**

The table status is displayed directly on the processed video.

---

### 4. Crowd Congestion and Heatmap

The project analyzes crowd density in the video using detected people.

A heatmap is generated based on the locations of detected people over the video frames.

The system also defines a crowd threshold of **5 people**. When the detected crowd count exceeds this threshold, a warning message is displayed:

`WARNING: CROWD CONGESTION!`

The heatmap is smoothed using Gaussian blur, normalized, converted into a color map, and blended with the original video frame.

---

### 5. Face Blurring

The project includes a face anonymization process.

YOLO is first used to detect people. The upper portion of each detected person is then examined using the OpenCV Haar Cascade face detector.

When a face is detected, Gaussian Blur is applied to the detected face.

If a face cannot be detected within the head region, the head region is blurred as a fallback method.

This functionality is used to help anonymize people appearing in the video.

---

## Combined Video Analytics

The project also includes a combined processing pipeline that integrates multiple analytics functions into a single video-processing workflow.

The combined pipeline performs:

* Person detection and tracking.
* Queue counting.
* Employee/staff area tracking.
* Table occupancy monitoring.
* Crowd counting.
* Crowd congestion warning.
* Heatmap generation.
* Tracking ID display.

The processed information is displayed directly on the video frames.

---

## Technologies Used

* Python
* Google Colab
* YOLOv8n
* Ultralytics
* ByteTrack
* OpenCV
* NumPy
* FFmpeg
* Google Drive

---

## Input Video

The project uses a video file stored in Google Drive.

The notebook mounts Google Drive and uses the video file as the input for the different computer vision tasks.

The notebook also includes functionality to search the Google Drive for a video file with a `.mp4`, `.MP4`, or `.mov` extension.

---

## How to Run

The project is implemented in a Google Colab notebook.

### Steps

1. Open `Smart_Vision_Restaurant_analytics_Project.ipynb`.
2. Open the notebook in Google Colab.
3. Run the required installation cells.
4. Mount Google Drive.
5. Make sure the input video is available in Google Drive.
6. Set or locate the video path.
7. Run the task cells sequentially.
8. Review the generated processed videos.

The notebook generates separate output videos for the different tasks, including queue analysis, staff tracking, table occupancy, heatmap analysis, and face blurring.

---

## Project Structure

```text
Smart-Vision-Restaurant-analytics-Project/
│
├── Smart_Vision_Restaurant_analytics_Project.ipynb
└── README.md
```

---

## Technical Documentation

The complete implementation is available in:

`Smart_Vision_Restaurant_analytics_Project.ipynb`

The notebook contains the implementation of the five video analytics tasks and the combined video-processing pipeline.

The main computer vision components include:

* YOLO person detection.
* YOLO tracking.
* ByteTrack tracking IDs.
* Polygon-based ROI analysis.
* Person counting.
* Table occupancy analysis.
* Crowd density analysis.
* Heatmap generation.
* OpenCV Haar Cascade face detection.
* Gaussian blur for face anonymization.
* Video encoding using FFmpeg.

---

## Version Control

Git and GitHub are used to manage the project and track changes through commits.

The project repository is publicly available and contains the project notebook and documentation.

---

## Training Program

This project was completed as part of the **Computer Vision for Developers Course** training program.

---

## Saudi Digital Academy

Saudi Digital Academy (SDAIA) GitHub account:

https://github.com/SDAIAAcademy

---

## Course Information

**Course:** Computer Vision for Developers   

**Project:** Smart Vision Restaurant Analytics Project

---

## Author

**Rawan Altaweel**
