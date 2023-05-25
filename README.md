# Gazebo ROS Demos

* License: GNU General Public License, version 3 (GPL-3.0)

Example robots and code for interfacing Gazebo, ROS2 and Moveit2

## Quick Start

Launch Gazebo with controller:

Open-loop position control

    ros2 launch rrbot_gazebo rrbot_world_position_control.launch.py 
Open-loop effort control

    ros2 launch rrbot_gazebo rrbot_world_effort_control.launch.py 

Test open-loop position control (JointTrajectoryController):

    ros2 run rrbot_description position_control_test 
Test open-loop effort control (JointGroupEffortController):

    ros2 run rrbot_description effort_control_test 

Or

    ros2 topic pub /effort_controllers/commands std_msgs/msg/Float64MultiArray "data:
    - 9.0
    - 6.0"

## Develop and Contribute

We welcome any contributions to this repo and encourage you to fork the project then send pull requests back to this parent repo. Thanks for your help!


## Notes

`gazebo_tutorials` and `rrbot_control` have not yet been ported to ROS2, but need to be.
