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

In order to succesfully run the code, you should have installed paho-mqtt and ROS.
MQTT Broker

The suggested MQTT Broker is Mosquitto. In order to install Mosquitto on Ubuntu follow this guide.
Test

In order to test the code:

    Check the Mosquitto broker status, if the broker is already active skip step 2.

    sudo service mosquitto status

    Start the Mosquitto broker.

    mosquitto

    In a new terminal tab launch the imu_bridge.

    roslaunch mqtt_ros_bridge imu_bridge.launch

    In a new terminal tab check the ROS topip /inertial, nothing should appear.

    rostopic echo /inertial

    In a new terminal tab publish a sensors/imu message to the local Mosquitto broker.

    mosquitto_pub -h localhost -t "sensors/imu" -m "acc;9.8;-0.3;0.5;vel;0.1;0.12;-0.4"

    In the terminal open at step 4 should appear the message received by the ROS master.

How to use mqtt_ros_bridge

The imu_brdige node is an example of how to use the bridge, summing up:

    Import bridge.py
    Create a class example_brigde that inherit from the bridge class.

    class example_bridge(bridge.bridge):

    Implement the msg_process function to map MQTT message to ROS message.
    Initialize the bridge and call the loop function in a ROS while loop.
