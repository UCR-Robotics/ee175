# ee175

## Installation
- We assume that the ROS workspace is at `~/catkin_ws`.
```
cd ~/catkin_ws/src
git clone https://github.com/UCR-Robotics/ee175
cd ..
catkin_make
```

## Usage
- To launch mobile base and sensors (camera and lidar) on the real robot
```
roslaunch ee175 bringup.launch
```
- To visualize the data from camera and lidar
```
roslaunch ee175 rviz.launch
```
- To launch a quick demo of manipulator using Moveit
```
roslaunch interbotix_moveit interbotix_moveit.launch robot_name:=rx150 use_actual:=true dof:=5
```
- To launch the manipulator for development
```
roslaunch interbotix_sdk arm_run.launch robot_name:=rx150
```

## Notes
- The manipulator and camera must directly connect to the onboard computer (rather than indirectly via USB hub). Please do not change this setup.

- For the documentation of manipulator, please refer to [the official repository](https://github.com/UCR-Robotics/interbotix_ros_arms).

- For safety purpose, please double check if the joint angles are valid (i.e. it will not cause the crash) before sending to the manipulator.


## Debug
- To check if the manipulator is connected. It is expected to see `ttyDXL`.
```
ls /dev | grep ttyDXL
```
