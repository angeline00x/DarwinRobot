# DarwinRobot
install Ubuntu in AWS Kloud

```
sudo apt update
sudo apt upgrade -y

sudo apt-get install git ros-melodic-desktop-full gazebo ros-melodic-gazebo-plugins ros-melodic-gazebo-ros ros-melodic-gazebo-ros-control ros-melodic-hector-gazebo ros-melodic-hector-gazebo-plugins ros-melodic-effort-controllers ros-melodic-joint-state-controller ros-melodic-joint-state-publisher ros-melodic-turtlebot-teleop 

cd ~
mkdir -p ros-darwin/src
cd ros-darwin/src
source /opt/ros/hydro/setup.bash
catkin_init_workspace

git clone https://github.com/HumaRobotics/darwin_description.git
git clone https://github.com/HumaRobotics/darwin_control.git
git clone https://github.com/HumaRobotics/darwin_gazebo.git
cd ..

rosdep install --from-paths src --ignore-src -r -y

catkin_make
source devel/setup.bash

export display=:1

roslaunch darwin_gazebo darwin_gazebo.launch
rosrun darwin_gazebo walker_demo.py

```
