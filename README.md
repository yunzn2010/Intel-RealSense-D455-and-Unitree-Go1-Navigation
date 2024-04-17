# Intel-RealSense-D455-and-Unitree-Go1-Navigation
This project deploy uses Intel RealSense D455 camera to deploy Visual SLAM on Unitree Go1 Robot.

We are still editing this page.

### Platform
The main board of this project is the Jetson Nano on the Unitree Go1 robot, with IP Address 192.168.123.15 (will explain this after).
Operating System: Ubuntu 18.04
ROS Version: Melodic

### Image Transfer
With the trasfer speed limitation of USB 2.1 port on Go1, we need to find alternative to send image from Intel RealSense D455 to the Jetson Nano. 

```
export ROS_MASTER_URI=http://192.168.123.15:11311
export ROS_HOSTNAME=192.168.123.87
roscore
```
