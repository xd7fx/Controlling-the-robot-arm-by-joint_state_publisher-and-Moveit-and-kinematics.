# Controlling the robot arm by joint_state_publisher, Moveit and kinematics.

This project involves setting up and controlling an Arduino-based robot arm using ROS (Robot Operating System) with RViz and Gazebo for simulation. MoveIt is used for motion planning and execution.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Building the Package](#building-the-package)
- [Launching RViz and Gazebo](#launching-rviz-and-gazebo)
- [Using joint_state_publisher_gui](#using-joint_state_publisher_gui)
- [Setting Up MoveIt for Motion Planning](#setting-up-moveit-for-motion-planning)
- [Using the MotionPlanning Interface in RViz](#using-the-motionplanning-interface-in-rviz)
- [Final Summary](#final-summary)

## Prerequisites

Ensure you have the following installed:
- ROS Noetic
- Git
- catkin

## Installation

1. **Navigate to the workspace directory:**
    ```bash
    cd ~/catkin_ws/src
    ```
2. **Install Git:**
    ```bash
    sudo apt install git
    ```
3. **Clone the repository:**
    ```bash
    git clone https://github.com/smart-methods/arduino_robot_arm
    ```
![لقطة الشاشة 2024aa-07-28 151245](https://github.com/user-attachments/assets/4eb7e331-5055-403c-9b76-81a78dd38114)

   
4. **Navigate back to the workspace directory:**
    ```bash
    cd ~/catkin_ws
    ```
5. **Install dependencies using rosdep:**
    ```bash
    rosdep install --from-paths src --ignore-src -r -y
    ```
6. **Install required ROS packages:**
    ```bash
    sudo apt-get install ros-noetic-moveit
    sudo apt-get install ros-noetic-joint-state-publisher
    sudo apt-get install ros-noetic-joint-state-publisher-gui
    sudo apt-get install ros-noetic-gazebo-ros-control
    sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
    ```
![لقطة الشاشة 2a024-07-28 151245](https://github.com/user-attachments/assets/eefafc0f-6abf-4583-81c3-71a50bc92e81)

## Building the Package

Build the package using:
```bash
catkin_make
```
![لقطة الشاشة 2024-07-dd8 151245](https://github.com/user-attachments/assets/0f0c7961-f175-4c6e-a5ae-af323e74bd89)
![لقطة الشاشة 2024-07-28 151446](https://github.com/user-attachments/assets/e44fcd3e-d909-4e63-b693-9612361e4644)


## Launching RViz and Gazebo
1. **Launch the RViz configuration:**
    ```bash
    roslaunch robot_arm_pkg check_motors.launch
    ```

![لقطة الشاشة 2024-07-28 151536](https://github.com/user-attachments/assets/ee5347cc-bdfc-4e8d-a402-738eef8c43fd)
![لقطة الشاشة 2024-07-28 151627](https://github.com/user-attachments/assets/35f47766-bed6-4162-ad0b-464c66ad9c32)

2. **Visualize the node and topic graph in ROS:
  ```bash
  rqt_graph
  ```
![لقطة الشاشة 2024-07-28 152019](https://github.com/user-attachments/assets/0f7fe6c5-19b1-4d89-b976-6ac6f0d07e61)

3. **Launch the Gazebo simulation:**
    ```bash
    roslaunch robot_arm_pkg check_motors_gazebo.launch
    ```
![لقطة الشاشة 2024-07-28 152531](https://github.com/user-attachments/assets/648c69d2-083a-498d-a94b-8bdade8cc6b3)


## Using joint_state_publisher_gui

1. ****Manually adjust the joint positions and see the updates in RViz and Gazebo in real-time:**
  ```bash
  rosrun robot_arm_pkg joint_states_to_gazebo.py
  ```
![لقطة الشاشة 2024-07-28 152956](https://github.com/user-attachments/assets/6c69176f-b49d-415f-bd35-92fc705eb479)


https://github.com/user-attachments/assets/ea9af932-9524-4e5e-99fc-8f9ae4b8fa3c

2. **Running rqt_graph
Visualize the node and topic graph in ROS:
  ```bash
  rqt_graph
  ```
![لقطة الشاشة 2024-07-28 153436](https://github.com/user-attachments/assets/3c7e16a0-7407-45f8-a224-2a98cac3a324)

## Setting Up MoveIt for Motion Planning
1. **Launch the MoveIt demo:**
    ```bash
    roslaunch moveit_pkg demo.launch
    ```
![لقطة الشاشة 2024-07-28 153723](https://github.com/user-attachments/assets/3b94a1ca-d2a7-4f95-9722-b57c3a261822)


2. **Launch the MoveIt demo with Gazebo:**
    ```bash
    roslaunch moveit_pkg demo_gazebo.launch
    ```
![لقطة الشاشة 2024-07-28 153855](https://github.com/user-attachments/assets/80c54f9b-3aae-46b9-b3d0-5278014f9cd4)
![لقطة الشاشة 2024-07-28 154457](https://github.com/user-attachments/assets/b0981daa-b30c-4c90-b7e3-a2359b2f1b2d)


https://github.com/user-attachments/assets/1f0c259d-3630-4dce-bd2b-b8aa4a40a469



## Using the MotionPlanning Interface in RViz
Open the MotionPlanning interface in RViz:

- Define commands
- Plan movements for the arm
- Control various planning settings
- Set planning time, velocity scaling, and acceleration scaling

## Final Summary
The environment is set up, the package is built, and the necessary launch files are executed to display the robot arm in RViz and Gazebo. MoveIt is used for motion planning and executing movements, allowing full control and testing of the robot arm in a 3D simulation environment.




