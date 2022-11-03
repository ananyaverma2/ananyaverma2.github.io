---
layout: post
title:  "Cluttered Picking"
# date:   2022-04-02 18:05:55 +0300
image:  02.jpg
tags:   PROJECT
---


## Overall functionality


<img align="right" width="34%" src="https://raw.githubusercontent.com/ananyaverma2/HEART_MET_cluttered_pick/main/images/overview.png">

- The robot perceives its environment and the data is published on the topics to which we subscribe to.
- Once we get the image of the environment, object detection 
is carried out using Faster-RCNN and the object labels along 
with its bounding boxes are detected.
- Then these 2D bounding boxes are used to calculate the centroid of the object which acts as a grasping position in 2D.
- This 2D position is converted to 3D position and the yaw is also calculated, which combinedly gives us the grasing 
pose of the object.
- This process is looped over for the cluttered picking task.


## How to run the code:

To run the code you have to run 2 terminals with the below mentioned commands:

#### Terminal-1
Run object detection code: <br/>
`roslaunch object_detection grasp_pose_estimation.launch`

#### Terminal-2
Publish images from rosbag files continuously using the `-l` argument<br/>
`rosbag play -l <path_to_bag_file/_.bag>`

**OR**

Connect to the youBot server at `export ROS_MASTER_URI=http://192.168.1.114:11311` for youBot-4 and `export ROS_MASTER_URI=http://192.168.1.142:11311` for youBot-2
