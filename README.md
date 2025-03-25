# `slam_gmapping`
SLAM (Simultaneous Localization and Mapping) is the computational problem of building or updating a map of an unknown environment while simultaneously keeping track of the robot's localization within it.

This ROS meta-package contains packages `openslam_gmapping` and `slam_gmapping` which is a ROS2 wrapper for OpenSlam's Gmapping. The wrapper has been successfully tested with *ROS Jazzy* by Rui P. Rocha on Mar. 2025. Using `slam_gmapping`, you can create a 2D occupancy grid map from laser scans and odometry collected by a mobile robot.

## Launch:

```bash
ros2 launch slam_gmapping slam_gmapping.launch.py
```

The node slam_gmapping subscribes to sensor_msgs/LaserScan on ros2 topic `scan`. It also expects appropriate TF to be available.

It publishes the nav_msgs/OccupancyGrid on `map` topic, the TF from `map` frame to `odom` frame and the TF from `odom` frame to `base_link` frame. 

Map Meta Data and Entropy is published on `map_metadata` and `entropy`, respectively.
