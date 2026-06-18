 Helmet Detection System
Overview
The Helmet Detection System is an AI-based computer vision application developed to automatically detect whether individuals are wearing safety helmets in images. The system utilizes the YOLO object detection framework for real-time object detection, OpenCV for image processing, Label Studio for dataset annotation, and Streamlit for an interactive user interface.

The project aims to improve safety compliance monitoring in construction sites, industrial environments, manufacturing facilities, and traffic surveillance systems by automating helmet detection and reducing dependence on manual inspection.

Objectives

Detect helmet and non-helmet instances in images.

Perform accurate object localization using bounding boxes.

Provide confidence scores for detected objects.

Enable easy testing through a user-friendly web interface.

Support safety monitoring and compliance verification.

Demonstrate the practical application of Artificial Intelligence in workplace safety.

 Features
Helmet and No-Helmet Classification

Multiple Person Detection

Bounding Box Visualization

Confidence Score Display

Streamlit-Based Dashboard

Dataset Analytics Module

Evaluation Metrics Dashboard

Adjustable Detection Threshold

Easy Deployment and Scalability


System Architecture
Input Image
     │
     ▼
Data Preprocessing (OpenCV)
     │
     ▼
YOLO Object Detection Model
     │
     ▼
Detection Results
(Helmet / No Helmet)
     │
     ▼
Bounding Box Rendering
     │
     ▼
Streamlit Dashboard Output



Technology Stack
Technology	Purpose
Python	Core Programming Language
YOLO	Object Detection Model
OpenCV	Image Processing and Visualization
Label Studio	Data Annotation
Streamlit	Web Application Interface
Ultralytics	Model Training and Inference

Project Structure
Helmet-Detection-System/
│
├── bestmodel/
	├── best.pt
├── app.py
├── data.yaml
├── Train.ipynb
├── Test.ipynb
├── result.py
├── test_model.py
├── requirements.txt
├── split_data.py
├── test_model.py
├── yolo26n.pt
└── README.md

Dataset Preparation
Classes
The dataset contains one object classes:

Helmet

Annotation
Dataset annotations are created using Label Studio and exported in YOLO-compatible format.

Recommended Dataset Split
Dataset	Percentage
Training	80%
Validation	20%


Installation
Clone Repository
git clone https://github.com/your-username/helmet-detection-system.git
cd helmet-detection-system
Create Virtual Environment
python -m venv venv
Activate Environment
Windows

venv\Scripts\activate
Linux / macOS

source venv/bin/activate
Install Dependencies
pip install -r requirements.txt
Training the Model
Configure the dataset in data.yaml:

path: dataset
train: train/images
val: valid/images

names:
  0: Helmet
Run model training:

yolo detect train model=yolo.pt data=data.yaml epochs=50 imgsz=640
The trained model weights will be stored in:

runs/detect/train/weights/best.pt

Running Detection
Using Python Script
python detect.py
Using YOLO CLI
yolo detect predict model=best.pt source=test.jpg
Running the Web Application
Launch the Streamlit dashboard:

streamlit run app.py
Open:

http://localhost:8501

Dashboard Modules
1. Project Overview
Provides:

Project Description

Objectives

Workflow Explanation

Technology Stack

2. Test Detection
Allows users to:

Upload Images

Perform Helmet Detection

View Detection Results

3. Dataset Analytics
Displays:

Class Distribution

Dataset Statistics

Annotation Summary

4. Evaluation Metrics
Shows:

Precision

Recall

F1 Score

mAP@50

mAP@50-95

Confusion Matrix

5. Settings
Provides:

Confidence Threshold Adjustment

Detection Parameter Configuration

Performance Evaluation
The system is evaluated using standard object detection metrics:

Metric	Description
Precision	Correct positive predictions
Recall	Actual positives detected
F1-Score	Balance between precision and recall
mAP@50	Detection accuracy at IoU = 0.50
mAP@50–95	Multi-threshold localization accuracy
Applications
Construction Site Safety Monitoring

Industrial Safety Compliance

Smart City Surveillance

Traffic Rule Enforcement

Workplace PPE Monitoring

Manufacturing Plant Safety Audits

Advantages
Automated Safety Inspection

Reduced Human Error

Faster Monitoring Process

Scalable Deployment

User-Friendly Interface

Near Real-Time Detection Capability

Limitations
Performance depends on dataset quality.

Detection accuracy may decrease under poor lighting conditions.

Small or heavily occluded helmets may be difficult to detect.

Current implementation focuses primarily on image-based detection.

 Future Enhancements
Real-Time CCTV Monitoring

Video Stream Processing

Mobile Application Integration

Cloud-Based Deployment

Edge AI Optimization

Multi-PPE Detection (Helmet, Vest, Gloves, Shoes)

Automated Safety Violation Reporting

Team Members
Shubhangi Saindane

Sayli Katkar

Akshata Shinde

Ruchita Mandlik

Project Guide
Abdullah Khan Sir

