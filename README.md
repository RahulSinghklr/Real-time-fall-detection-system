# Real-time-fall-detection-system
# Fall Detection System

## Introduction
Falls are a leading cause of injury, particularly among the elderly, making fall detection crucial for enhancing safety. This project leverages advanced computer vision techniques to accurately detect falls in real-time, providing timely alerts to prevent severe consequences.

## Motivation
Falls are the second leading cause of unintentional injury deaths worldwide, with over 684,000 deaths annually according to the WHO. Adults over 60 are most at risk, highlighting the need for effective fall detection systems. This project aims to reduce fall-related injuries by providing real-time monitoring and alerts.

## Solution Overview
This project implements a robust fall detection system using the following technologies:

- **Mediapipe**: Used for pose estimation to detect key landmarks on the human body.
- **OpenCV**: Utilized for drawing and UI visualization tasks.
- **YOLOv5 and YOLOv8**: Deep learning models trained specifically for fall detection, ensuring high accuracy in real-time scenarios.
- **Threading**: Ensures uninterrupted video processing while sending timely email alerts.

## Technologies and Libraries Used
1. **Mediapipe**: For pose estimation, enabling precise landmark detection.
2. **OpenCV**: Powers the visualization of detection results, including drawing lines and highlighting areas of interest.
3. **YOLOv5 and YOLOv8**: State-of-the-art object detection models trained to identify falls in video streams.
4. **Threading**: Manages asynchronous tasks like email notifications, ensuring smooth operation.

## Methodology
### Measuring Falls
The system measures the distance between the body’s center of gravity (C.G) and the foot C.G. A fall is detected if this distance exceeds a predefined threshold (90 pixels or 75% of the body height).

### Heinrich's Law Application
Based on Heinrich's Law, which suggests that frequent near-misses can lead to a major accident, the system counts and monitors fall instances to trigger preventive measures before reaching a critical number.

### Perspective Consideration
The system adjusts for perspective by comparing the body's C.G with the distance between the feet, ensuring accurate fall detection regardless of the object's distance from the camera.

### Regional Fall Calculation
The system tracks the center point of the feet within predefined regions to accurately detect and log falls.

## Training the YOLO Models
### Dataset Preparation
- Collect and annotate images showing falls and non-falls.
- Split the data into training and validation sets.

### Installation and Setup
```bash
pip install torch opencv-python
git clone https://github.com/ultralytics/yolov5
cd yolov5
```
## Data Organization
- Organize images and labels according to YOLO’s directory structure.
- Update the dataset configuration file with the correct paths.

## Model Training
### For YOLOv5
```bash
python train.py --img 640 --batch 16 --epochs 100 --data data.yaml --weights yolov5s.pt
```
### For YOLOv8
```bash
python train.py --img 640 --batch 16 --epochs 100 --data data.yaml --weights yolov8s.pt
```
## Model Evaluation
Evaluate model performance using the validation set:
```bash
python val.py --data data.yaml --weights runs/train/exp/weights/best.pt --img 640
```
![image alt](https://github.com/RahulSinghklr/Real-time-fall-detection-system/blob/main/11.png)
![image alt](https://github.com/RahulSinghklr/Real-time-fall-detection-system/blob/main/22.png)
![image alt](https://github.com/RahulSinghklr/Real-time-fall-detection-system/blob/main/33.png)
![image alt](https://github.com/RahulSinghklr/Real-time-fall-detection-system/blob/main/44.png)
![image alt](https://github.com/RahulSinghklr/Real-time-fall-detection-system/blob/main/55.png)
![image alt](https://github.com/RahulSinghklr/Real-time-fall-detection-system/blob/main/66.png)
![image alt](https://github.com/RahulSinghklr/Real-time-fall-detection-system/blob/main/77.png)
![image alt](https://github.com/RahulSinghklr/Real-time-fall-detection-system/blob/main/88.png)
![image alt](https://github.com/RahulSinghklr/Real-time-fall-detection-system/blob/main/99.png)

