FACE RECOGNITION ATTENDANCE SYSTEM:
This project is a Flask-based web application that automates student attendance using face recognition technology. It consists of three main modules:

1. DATASET CREATION (DatasetCreation.py):
Captures grayscale face images using the IP Webcam stream and Mediapipe Face Detection, storing them in labeled folders for training.

Input: Student's name via a registration form

Output: 100 face images (130x100 grayscale) per student saved in Dataset/{student_name}

2. FACE RECOGNITION & ATTENDANCE (FaceRecognition.py):
Recognizes students in real-time video feed and marks attendance in a CSV file per subject.

Trains an LBPH Face Recognizer using the images in the Dataset/ directory

Uses Mediapipe for real-time face detection

Matches faces and writes names with timestamp to attendance_{subject}.csv

3. ATTENDANCE MARKING (CSV):
Each subject (e.g., .NET, EVS, etc.) has its own CSV file:
attendance_dotnet.csv
attendance_evs.csv
...

Each entry contains:

Name

Timestamp of attendance

4. WEB INTERFACE:
Subject selection from dropdown

Live webcam feed

Auto face recognition and attendance marking

Simple and user-friendly UI using Flask templates

REQUIRMENTS:
Python 3.10+

Flask

OpenCV (cv2)

Mediapipe

NumPy

NOTES:
IP Webcam must be set up on a mobile device (http://<IP>:8080/video)

Run both scripts separately:

First: DatasetCreation.py to collect face data

Then: FaceRecognition.py to perform recognition and mark attendance
