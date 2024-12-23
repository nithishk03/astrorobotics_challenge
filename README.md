# Astrorobotics Challenge
To Run the Solution for the Challenge first 

Create a workspace for example 

mkdir astrorobot_ws
cd astrorobot_ws

Create a .rosinstall file in the root directory of your workspace. 

gedit .rosinstall

Add the following lines to .rosinstall:

- git: {local-name: src, uri: 'https://github.com/nithishk03/astrorobotics_challenge.git', version: main}
- git: {local-name: src/aws-robomaker-small-warehouse-world, uri: 'https://github.com/aws-robotics/aws-robomaker-small-warehouse-world.git', version: ros2}

Save the .rosinstall file in your workspace 

Now run the commands

rosws update
rosdep install --from-paths . --ignore-src -r -y
colcon build

Now source this workspace like,
source install/setup.bash

now execute the following command spawn the robot in gazebo envoirment

ros2 launch robot_bringup bringup.launch.py

now execute the following command spawn the navigation stack 2 module

ros2 launch robot_navigation navigation.launch.py 

finally excute this  node to make to robot move through 3 diffrent waypoints 

ros2 run robot_navigation waypoint_node

Thank You



