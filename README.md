# Astrorobotics Challenge

This repository contains the solution for the Astrorobotics Challenge. Follow the steps below to set up and run the solution.

---

## Setup Instructions

### Step 1: Create a Workspace
Create a new workspace for the project:

```bash
mkdir astrorobot_ws
cd astrorobot_ws
```

### Step 2: Create a .rosinstall File

2.1 Create a .rosinstall file in the root directory of your workspace:


```bash
gedit .rosinstall
```
2.2 Add the following lines to .rosinstall:

```bash
- git: {local-name: src, uri: 'https://github.com/nithishk03/astrorobotics_challenge.git', version: main}
- git: {local-name: src/aws-robomaker-small-warehouse-world, uri: 'https://github.com/aws-robotics/aws-robomaker-small-warehouse-world.git', version: ros2}
```

2.3 Save the .rosinstall file.
---
### Step 3: Install Dependencies and Build the Workspace

Run the following commands:

```bash
rosws update
rosdep install --from-paths . --ignore-src -r -y
colcon build
```

---
### Step 4: Source the Workspace

Source the workspace to set up the environment:

```bash
source install/setup.bash
```

---

### Step 5: Run the Simulation and Navigation
5.1. Spawn the Robot in the Gazebo Environment

Run the following command:

```bash
ros2 launch robot_bringup bringup.launch.py
```

5.2. Launch the Navigation Stack:

```bash
ros2 launch robot_navigation navigation.launch.py
```

5.3. Move the Robot Through Waypoints

```bash
ros2 run robot_navigation waypoint_node
```

#Thank you!! <3
