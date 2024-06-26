# Effects of Facial Recognition on False Arrests

This repository contains all the materials related to my thesis project conducted as part of the requirements for the Bachelor of Science degree in Computer Science at [Your University]. The thesis explores the impact of Facial Recognition Technology (FRT) on false arrests, with a focus on how it integrates with eyewitness identifications in the law enforcement process.

## Project Overview

Facial Recognition Technology (FRT) is increasingly used in various security and law enforcement applications. Despite its growing adoption, concerns about its reliability and the ethical implications regarding privacy and justice are prevalent. This project examines how inaccuracies in FRT, combined with eyewitness testimonies, can lead to wrongful convictions, and how these biases disproportionately affect minority communities.

## Research Questions

- How does the use of facial recognition technology by law enforcement influence the accuracy of eyewitness identifications and the rate of wrongful arrests and convictions?
- What are the implications of facial recognition technology's use in law enforcement for privacy and racial equity within the criminal justice system?

## Methodology

This study employs a mixed-methods approach, integrating both qualitative interviews with law enforcement personnel and quantitative analysis using data simulation on Python to evaluate FRT's reliability and its impact on wrongful arrests.

## Installation

Instructions to set up the project environment:

githubname: ericsledge

## REQUIREMENTS
Raspberry Pi: Ensure it’s running Raspbian OS.
Camera: You can opt for the Raspberry Pi’s native camera module or a compatible USB webcam.
Libraries: CVZone and OpenCV are the mainstays for our computer vision tasks.
Python: Version 3.6 or later is recommended for compatibility and performance.

## INSTALLATION STEPS
Setting up your Raspberry Pi:
Begin with a Raspberry Pi with Raspbian OS already installed.
Connect your chosen camera module or USB webcam to the Raspberry Pi. Ensure that it’s compatible and properly detected by the system.
Install OpenCV:

OpenCV is a foundational library for computer vision. Install it using the following commands:

sudo apt-get update
sudo apt-get install libopencv-dev python3-opencv
Install CVZone:

With OpenCV in place, you can now proceed to install CVZone:

pip3 install cvzone

## FACE DETECTION

Capture video from the camera:

import cv2
cap = cv2.VideoCapture(0)

Use CVZone to detect face:

import cvzone
from cvzone import FaceDetectionModule
face_detector = FaceDetectionModule.FaceDetector()

while True:
    success, img = cap.read()
    img, list_faces = face_detector.findFaces(img)
    cv2.imshow("Face Detection", img)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
