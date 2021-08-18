[Task2.pdf](https://github.com/bedaromar/Use-Turtlebot3-with-SLAM-approach-to-create-and-save-a-map/files/7003649/Task2.pdf)
# Use-Turtlebot3-with-SLAM-approach-to-create-and-save-a-map
I suggest to see the task through the PDF file attached above..

This is my Second task in Robotics and AI department at SMART METHODS summer training, And In this file I'll explain the steps for using robot arm in ROS.

## Detailed Steps:

1- Open the link  https://emanual.robotis.com/docs/en/platform/turtlebot3/overview/#overview and from the option (Quick start Guide)
Choose PC Setup and download the codes

![Circuit Diagram](https://github.com/bedaromar/Use-Turtlebot3-with-SLAM-approach-to-create-and-save-a-map/blob/main/screenshot/Screenshot%201443-01-10%20at%2003.09.31.png)
 -  `sudo apt update`
- Install ROS 1 on Remote PC
-  `$ sudo apt-get update`
-  `$ sudo apt-get upgrade`
-  `$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_kinetic.sh`
-  `$ chmod 755 ./install_ros_kinetic.sh`
-  `$ bash ./install_ros_kinetic.sh`

- Install Dependent ROS 1 Packages
-  `$ sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy \
  ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc \
  ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan \
  ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python \
  ros-kinetic-rosserial-server ros-kinetic-rosserial-client \
  ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server \
  ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro \
  ros-kinetic-compressed-image-transport ros-kinetic-rqt* \
  ros-kinetic-gmapping ros-kinetic-navigation ros-kinetic-interactive-markers`
  
- Install TurtleBot3 Packages
-  `$ sudo apt-get install ros-kinetic-dynamixel-sdk`
-  `$ sudo apt-get install ros-kinetic-turtlebot3-msgs`
-  `$ sudo apt-get install ros-kinetic-turtlebot3`
-  `$ sudo apt-get remove ros-kinetic-dynamixel-sdk`
-  `$ sudo apt-get remove ros-kinetic-turtlebot3-msgs`
-  `$ sudo apt-get remove ros-kinetic-turtlebot3`
-  `$ mkdir -p ~/catkin_ws/src`
-  `$ cd ~/catkin_ws/src/`
-  `$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/DynamixelSDK.git`
-  `$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git`
-  `$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git`
-  `$ cd ~/catkin_ws && catkin_make`
-  `$ echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc`

- Set TurtleBot3 Model Name
-  `$ echo "export TURTLEBOT3_MODEL=waffle" >> ~/.bashrc`
-  `$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch`



2- The turtlebot and its environment have been successfully installed

![Circuit Diagram](https://github.com/bedaromar/Use-Turtlebot3-with-SLAM-approach-to-create-and-save-a-map/blob/main/screenshot/Screenshot%201443-01-10%20at%2003.09.42.png)

3- The turtlebot has been controlled and the map has been drawn successfully

![Circuit Diagram](https://github.com/bedaromar/Use-Turtlebot3-with-SLAM-approach-to-create-and-save-a-map/blob/main/screenshot/Screenshot%201443-01-10%20at%2003.09.53.png)

4- Finally save a map 
-  `$rosrun map_server map_saver -f ~/map`
