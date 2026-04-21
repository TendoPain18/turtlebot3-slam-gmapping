# TurtleBot3 SLAM with Gmapping 🗺️🤖

A step-by-step tutorial for building a 2D occupancy grid map of an unknown environment using TurtleBot3 in Gazebo with ROS Gmapping SLAM. Covers workspace setup, Gmapping configuration, RViz visualization, and saving the generated map.

<div align="center">
  <img src="images/thumbnail.png" alt="Project Thumbnail" width="700"/>
</div>

<br>
<div align="center">
  <a href="https://codeload.github.com/TendoPain18/turtlebot3-slam-gmapping/legacy.zip/main">
    <img src="https://img.shields.io/badge/Download-Files-brightgreen?style=for-the-badge&logo=download&logoColor=white" alt="Download Files" style="height: 50px;"/>
  </a>
</div>

## 📋 Description

This mini project demonstrates how to implement SLAM (Simultaneous Localization and Mapping) on a simulated TurtleBot3 robot using the **Gmapping** package in ROS Noetic. The robot navigates through the `turtlebot3_world` Gazebo environment using keyboard teleoperation while building a 2D map in real-time, which is then saved using `map_server`.

The repository includes the `slam_gmapping` ROS package with a pre-configured Gmapping launch file and the saved output map.

## 🎥 Demo Video

The `mini_project_1.mp4` video covers the full workflow — workspace setup, launching the simulation, running Gmapping, driving the robot to build the map, and saving it.

## ✨ What This Project Covers

- Creating a catkin workspace and sourcing it
- Cloning the TurtleBot3 simulations repository (Noetic branch)
- Modifying `turtlebot3_world.launch` to add `robot_state_publisher` and `joint_state_publisher`
- Creating a `slam_gmapping` ROS package with a tuned Gmapping launch file
- Launching the Gazebo simulation and Gmapping simultaneously
- Visualizing the map and laser scan in RViz
- Driving the robot with `teleop_twist_keyboard` to explore the environment
- Saving the generated map as `.pgm` + `.yaml` using `map_server`

## 🚀 Quick Start

```bash
# 1. Set TurtleBot3 model
export TURTLEBOT3_MODEL=waffle

# 2. Launch Gazebo simulation
roslaunch turtlebot3_gazebo turtlebot3_world.launch

# 3. Launch Gmapping (new terminal)
roslaunch slam_gmapping slam_gmapping.launch

# 4. Open RViz, set Fixed Frame → map, add Map (/map) and LaserScan (/scan)

# 5. Drive the robot (new terminal)
rosrun teleop_twist_keyboard teleop_twist_keyboard.py

# 6. Save the map (new terminal)
rosrun map_server map_saver -f ~/catkin_ws/src/maps/my_map
```

## 🗺️ Gmapping Key Parameters

| Parameter | Value | Description |
|-----------|-------|-------------|
| `particles` | 100 | Number of particles in the particle filter |
| `maxUrange` | 50.0 m | Maximum usable sensor range |
| `map_update_interval` | 2.0 s | How often the map is updated |
| `delta` | 0.05 | Map resolution (meters/cell) |
| `base_frame` | `base_footprint` | Robot base frame |
| `odom_frame` | `odom` | Odometry frame |

## 📁 Repository Structure

```
turtlebot3-slam-gmapping/
├── mini_project_1/
│   └── catkin_ws/
│       └── src/
│           ├── slam_gmapping/           # ROS package
│           │   ├── launch/
│           │   │   └── slam_gmapping.launch
│           │   ├── CMakeLists.txt
│           │   └── package.xml
│           └── maps/                    # Saved map output
│               ├── mini_project_1_map.pgm
│               └── mini_project_1_map.yaml
└── mini_project_1.mp4                   # Tutorial demo video
```

## 🛠️ Requirements

- Ubuntu 20.04
- ROS Noetic
- TurtleBot3 simulation packages: `ros-noetic-turtlebot3-simulations`
- Gmapping: `ros-noetic-slam-gmapping`
- Map server: `ros-noetic-map-server`
- Teleop: `ros-noetic-teleop-twist-keyboard`

## 🙏 Acknowledgments

- ROBOTIS TurtleBot3 simulation packages

<br>
<div align="center">
  <a href="https://codeload.github.com/TendoPain18/turtlebot3-slam-gmapping/legacy.zip/main">
    <img src="https://img.shields.io/badge/Download-Files-brightgreen?style=for-the-badge&logo=download&logoColor=white" alt="Download Files" style="height: 50px;"/>
  </a>
</div>

## <!-- CONTACT -->
<!-- END CONTACT -->

## **Map the unknown — one laser scan at a time! 🗺️✨**
