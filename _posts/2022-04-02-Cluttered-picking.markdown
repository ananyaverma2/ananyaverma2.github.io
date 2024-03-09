---
layout: post
title:  "Cluttered Picking"
# date:   2022-04-02 18:05:55 +0300
image:  04.jpg
tags:   PROJECT
---


The cluttered picking task is performed on the youBot in the B-it-bots lab and is divided into two parts:

1. Perception 
2. Manipulation and navigation

This project contains the code to carry out the perception part of the pipeline. The input and outputs are as follows:

**Input:** images of the objects as perceived by the camera of the robot \
**Output:** 4D pose of the object

### Perception pipeline

<img width="34%" src="https://raw.githubusercontent.com/ananyaverma2/HEART_MET_cluttered_pick/main/images/overview.png">

- The robot perceives its environment and the data is published on the topics to which we subscribe to.
- Once we get the image of the environment, object detection 
is carried out using Faster-RCNN and the object labels along 
with its bounding boxes are detected.
- Then these 2D bounding boxes are used to calculate the centroid of the object which acts as a grasping position in 2D.
- This 2D position is converted to 3D position and the yaw is also calculated, which combinedly gives us the 4D grasing pose of the object.
- This process is looped over for the cluttered picking task.

