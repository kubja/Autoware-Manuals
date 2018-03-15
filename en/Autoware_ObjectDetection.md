# Autoware Object Detection Manual 

## For Autoware *ver.2017.Sep*

## Table of contents


This document explains object detection.

# Overview of object detection

There are two methods used for object detection: 

* computer vision,
* lidar pointcloud detector.



## Computer vision

In Autoware configuration, front monocular camera is assumed. Computer vision detection is therefore still utilizing lidar point cloud to determine distances. This functionality is provided by *cv_tracker* package. Currently, pedestrian/car tracking is available.

There are four steps:

1. **Detection**: outputs position of objects in input image;
2. **Ranging**: determines distance from point cloud, needs reprojection of the pointcloud to camera frame (points2image);
3. **Tracking**: tracks the objects over time between consecutive camera frames;
4. **Reprojection**: projects the position of the object from camera frame to map frame.

Camera-lidar pair needs to be precisely calibrated to determine the distance of the object. The calibration can be done using internal tool available in GUI at Sensing/Calibration Toolkit. Once you calibrate the camera position, you should publish the /projection_matrix and /camera_info topic. Points2image node fuses the pointcloud with the camera calibration, extrinsic and intrinsic parameters are necessary. 

### Detection

In Autoware, there are several different algorithms available for pedesterian/car detection:

* **yolo2_wa**: Yolo is very fast object detector using neural network to predict bounding boxes and other neural network for classification. Requires Darknet.
* **dpm_ocv** : Deformable Part-based Models classifier from OpenCV. It is based on a Dalal-Triggs detector that uses a single filter on histogram of oriented gradients (HOG) features to represent an object category. 
* **dpm_ttic** : other implementation of **Deformable Part-based Models** classifier residing in residing in "computing/detection/lib/image/dpm_ttic" package
* **rcnn_msr** : Fast Region-based Convolutional Networks for object detection created by Ross Girshick at Microsoft Research. The work is described in https://arxiv.org/abs/1504.08083. Requires Caffe. *This package is now deprecated and there is a faster version.*
* **ssd_unc** : Single Shot MultiBox Detector. SSD is an unified framework for object detection with a single network. You can use the code to train/evaluate a network for object detection task. Details: https://arxiv.org/abs/1512.02325 .


### Configuration



## Lidar



### Visualization

Package *viewers* contain useful tools to visualize the processed data. 

To display PointsImage overlayed on the original image.

```
rosrun viewers points_image_viewer _viewer_type:=points_image_viewer _points_topic:=/prius/front_camera/points_image _image_raw_topic:=/prius/front_camera/image_raw
``` 

