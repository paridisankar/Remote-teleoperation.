# Remote-teleoperation.

For the Remote-teleoperation to control the simulated robot “remotely”

to control the robot
with a “remote” pc that does not have ROS

or this we will use the MQTT protocol 

For that i have used mqtt_ros_bridge it is the main bridge controll for the ros to other computer

for get the mqtt_ros_pkg 

cd catkin_ws

cd src

git clone https://github.com/paridisankar/Remote-teleoperation..git

cd src

catkin_make 

This is the step to downlode the mqtt_brige ros pkg 

MQTT ROS Bridge

This Bridge allows to subscribe to MQTT topics and publish contents of MQTT messages to ROS. It is not yet possible to pulish to MQTT from ROS.
Installation

Clone the repository in the source folder of your catkin workspace.

git clone https://github.com/paridisankar/Remote-teleoperation..git

Dependencies

# ROS cmd_vel MQTT bridge

## Introduction

A ROS package to use any mqtt broker for storing the /cmd_vel topic. Uses the paho_mqtt client package.

This topic can then be used subscribed by any MQTT client.
Useful for resource constrained IoT Robots .


## Setup

**Requires ROS**
(A guide for installation can be found [here](http://wiki.ros.org/ROS/Installation))


### How to build
```
$ cd /path/to/ws/src
$ git clone <this repository>
$ cd ..
$ rosdep install --from-paths src --ignore-src -r -y --reinstall
$ catkin_make
$ source ./devel/setup.sh

## Usage

` $ roslaunch cmd_vel_mqtt cmd_vel_pub.launch`

For example you can use this along with the teleop_twist_keyboard package for keyboard control.

` $ rosrun teleop_twist_keyboard teleop_twist_keyboard.py


Work in progress.


