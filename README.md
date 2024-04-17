# Unitree_Go1_Navigation_Intel_RealSense_D455
This project uses Intel RealSense D455 camera to deploy Visual SLAM on Unitree Go1 Robot.

For those who can read Mandarin, I highly recommand you read this page:
[https://www.yuque.com/ironfatty]

> We are still editing this page. Please do not directly follow my page.

### Hardware
1. 1x Unitree Go1 Robot Education (Jetson Nano Version) set
2. 1x Raspberry Pi 4B
3. 1x SD Card
4. 1x mini HDMI to HDMI cable
5. 1x HDMI cable
6. 1x TP-Link TL-WN722N 150Mbps High Gain Wireless USB Adapter (This is essential)
7. Ethernet Cable

### Platform
The main board of this project is the Jetson Nano on the Unitree Go1 robot, with IP Address 192.168.123.15 (will explain this after).
Operating System: Ubuntu 18.04
ROS Version: Melodic

## ROS: Master-Slave Structure
With the trasfer speed limitation of USB 2.1 port on Go1, we need to find alternative to send image from Intel RealSense D455 to the Jetson Nano. Our team decided to use an external Raspberry Pi 4B(8G) to connect to the Intel RealSense D455 camera and send the captured data to Go1's Jetson Nano through ethernet cable. Therefore, we have a master-slave structure in our system.

ROS Master: Jetson Nano <br>
ROS Slave: Raspberry Pi 4B

### ROS: Master-Slave Clock Synchronization
Our systme uses "chrony" packages. To install it, open the terminal and type:
```
sudo apt install chrony
```

### ROS: Master-Slave Communication
On Jetson Nano:
```
export ROS_MASTER_URI=http://192.168.123.15:11311
export ROS_HOSTNAME=192.168.123.15
roscore
```
On Raspberry Pi:
```
export ROS_MASTER_URI=http://192.168.123.15:11311
export ROS_HOSTNAME=192.168.123.87
```

## Mapping: Visual SLAM (rtabmap)
Please refer to this page: [https://wiki.ros.org/rtabmap_ros/Tutorials/HandHeldMapping]

## Path Planning: RRT* and OMPL
In this project, we use Open Motion Planning Library to implement RRT*.
To install the OMPL:
```
sudo apt-get install ros-melodic-ompl
```
Please change the "melodic" to the correct ROS version of you device.

## Controller: Following the Waypoints

## Obstacle Avoidance Strategy

## Troubleshooting


