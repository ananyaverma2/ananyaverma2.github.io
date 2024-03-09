---
layout: post
title:  "Segmentation of Mars Terrain Using Classical Computer Vision Techniques"
# date:   2022-04-02 18:05:55 +0300
image:  mars.png
tags:   PROJECT
---


## Overall functionality

This project explores the segmentation of the topography on Mars by analysing data gathered by rovers like Curiosity, Perseverance, and Spirit using traditional computer vision techniques. Automated identification of rocks, sand, and dust is essential for comprehending the surface of the planet and enabling rover navigation due to the heterogeneous Martian topography. We hope to address the difficulties caused by different lighting circumstances by utilising techniques such as edge detection and RGB segmentation, which allow for accurate segmentation based on texture and slight colour differences. The study, which is centred on the Perseverance rover's photos from the Jezero crater [i1], attempts to classify the surface of Mars into three groups: Rock, Bedrock, and Sand. This will aid in the investigation and examination of possible indicators of prehistoric microbial life in certain areas, such as the Jezero delta.

<img src="https://raw.githubusercontent.com/ananyaverma2/mars_terrain_segmentation/main/images/panorama.png">

[i1]: https://mars.nasa.gov/resources/26978/detailed-panorama-of-mars-jezero-crater-delta/

## Steps followed

-  Segment sand using Thresholding
-  Extract the rocks from the image
-  Edge detection for identifying rocks and bedrocks
-  Segmenting rocks and bedrocks with KNN
- Segmenting rocks and bedrocks
  - Superimposing with contour
  - Superimposing with KNN
-  Final result

## Input image


<img src="https://raw.githubusercontent.com/ananyaverma2/mars_terrain_segmentation/main/images/cv_test_images_1.png">

## Output image

<img src="https://raw.githubusercontent.com/ananyaverma2/mars_terrain_segmentation/main/final_results/image1/final_Seg_all_3_classes_denoise.jpg">

