---
layout: post
title:  "Object placement using Point Cloud Library (PCL)"
# date:   2022-10-07 18:05:55 +0300
image:  pcl.png
tags:   PROJECT
---

# Object Placement using Point Cloud Library

This project focuses on identifying possible drop points for a robot to place an object using a point cloud obtained from an RGB-D sensor. The sensor, mounted on the robot (Lucy), captures color and depth information, which is then processed to determine suitable locations for object placement.

<img width="95%" src="https://raw.githubusercontent.com/ananyaverma2/PCL_object_placement/master/img/depth.jpeg">
<img width="95%" src="https://raw.githubusercontent.com/ananyaverma2/PCL_object_placement/master/img/point_cloud.jpeg">

### Dependencies
* Python 3
* NumPy
* Matplotlib
* SciPy
* Point Cloud Library (PCL)

### Methodology

* The point cloud (cloud.pcd) is transformed based on the camera's pose relative to the robot's base.
* Points are then ranked using a point ranking algorithm, considering their angles with respect to the Z-axis.
* The output is visualized in a 3D plot, where suitable drop points for object placement are highlighted in red.

**Github repository:** The repository can be found [here](https://github.com/ananyaverma2/PCL_object_placement)