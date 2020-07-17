# MilieuAutoNav

Currently, this project is being developed for Ubuntu 18.04 and ROS Melodic

The Sensors used for this project:
- Rplidar A2 Lidar Scanner
- Intel RealSense D435i Depth Camera

Packages in use:
- hector_slam
- rplidar_ros
- realsense-ros

All the above packages have github repos of their own

Running these packages together I use the following terminal commands:

For the hector_slam:
- roslaunch hector_slam_launch tutorial.launch

For the rplidar_ros:
- roslaunch rplidar_ros rplidar.launch

For the realsense-ros:
- roslaunch realsense2_camera rs_camera.launch filters:=pointcloud enable_infra1:=false enable_infra2:=false

(the reason for the tags on the realsense launch file is that the amount of data attempting to run over the current connection is too much to handle, 
and it ends up causing errors. This removes the infrared data we don't need at the moment to make sure that the data we need is properly transmitting.)
