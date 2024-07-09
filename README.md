# Two wheel Simple Robot SLAM and Gmapping

![Robot view](/sick_robot_description/robot_view.png)


This project demonstrates how to implement SLAM (Simultaneous Localization and Mapping) using the Gmapping algorithm on a two-wheel robot with two caster wheels.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository contains the necessary code and instructions to build and run a two-wheel robot equipped with SLAM capabilities using the Gmapping algorithm. The robot uses two main wheels for movement and two caster wheels for balance.

## Features

- Implementation of SLAM using the Gmapping algorithm.
- mapping capabilities.
- Real-time visualization using RViz.

## Requirements

- ROS (Robot Operating System) Noetic
- Catkin workspace
- Ubuntu 20.04

## Installation

### Step 1: Clone the Repository

```
mkdir -p catkin_ws/src
cd catkin_ws/src
git clone https://github.com/SAJIB3489/sick_robot.git
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src -r -y
source /opt/ros/noetic/setup.bash
source ~/catkin_ws/devel/setup.bash
catkin_make
```


### Step 2: Launch

**Launch gazebo simulation**
```
roslaunch sick_robot_description gazebo.launch
```


**Launch RViz** Open a new Terminal.
```
roslaunch sick_robot_description display.launch
```

**Start Gmapping** Open a new Terminal.
```
roslaunch sick_robot_description mapping.launch
```







1. To save the map
```
rosrun map_server map_server -f robot_map
```

2. keyboard controller
```
rosrun teleop_twist_keyboard teleop_twist_keyboard.py