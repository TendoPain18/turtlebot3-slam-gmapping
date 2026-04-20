# **TurtleBot3 Navigation Assignment**

**Task**: Use your SLAM-generated map to navigate the TurtleBot3 in Gazebo.

#### **1. Launch Simulation & Navigation**

```bash
export TURTLEBOT3_MODEL=burger
roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

In a **new terminal**:

```bash
roslaunch turtlebot3_navigation turtlebot3_navigation.launch 
```

#### **2. Localize the Robot**

- In RViz:
  1. Click **"2D Pose Estimate"**.
  2. Click/drag on the map where the robot *actually* is in Gazebo.

#### **3. Navigate**

- Use **"2D Nav Goal"** in RViz to send destinations.

#### **4. Submit**

- A screenshot of RViz showing successful navigation.
- A 2-line note on any issues faced.
