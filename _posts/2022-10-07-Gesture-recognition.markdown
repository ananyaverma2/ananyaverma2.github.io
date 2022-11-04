---
layout: post
title:  "Gesture Recognition"
# date:   2022-10-07 18:05:55 +0300
image:  gesture_title_image.png
tags:   PROJECT
---

This task was performed in [METRICS HEART-MET Competition](https://metricsproject.eu/healthcare/heart-met-competition/) at [Cobot Maker Space](https://cobotmakerspace.org/), University of Nottingham, United Kingdom.

This functionality benchmark assesses the robot’s capability of recognizing gestures performed by a human. The robot is placed in front of a human who performs a gesture. The robot needs to recognize the gesture being performed by the human.

## Project Description:

The gestures (dependent variable) will be chosen from a list consisting of:

1. **Head gestures:** The head gestures are detected using the Haarcascade Classifier [haarcascade_frontalface_alt.xml](https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_frontalface_alt.xml) to identify the face and then detect the movements in the x and y direction relative to the center of the face. The following head gestures are detected in this project.
    - Nodding
    - Shaking head

2. **Hand gestures:** The hand gestures are detected using the [Mediapipe Hands](https://google.github.io/mediapipe/solutions/hands.html) to detect the 21 3D landmarks of a hand as shown in the figure below. The following hand gestures are detected in this project.
    - Stop sign
    - Thumb down
    - Thumbs up
    - Waving

<p align="center">
  <img align="center" width="75%" src="https://raw.githubusercontent.com/ananyaverma2/gesture_recognition_benchmark/master/images/hand_landmarks.png">
</p>



Our team secured First place in the competition and the details can be found [here](https://www.h-brs.de/de/inf/b-it-bots-erfolgreich-auf-heart-met-wettbewerb-nottingham).


**Github repository:** The repository can be found [here](https://github.com/ananyaverma2/gesture_recognition_benchmark)