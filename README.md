
## MAEG Final Project --Grab Coke --Student ID :1155139063
```
The git code address of this repository :
https://github.com/abcshi222/ROS_Pro.git

My youbube video of Grab coke :
https://www.youtube.com/watch?v=ZL8SRAqf2u4

```

## Summary


In this project, the coke can should be grabbed using a SIDE APPROACH
If successful, you will have learned to work with additional objectsin the world, and to devise different
strategies for grasping.

The coke can is a standard Gazebo model that should be available to you if you have downloaded gazebo 
models

## Quickstart
```
To run the code: 
◦ Start Baxter (baxter.sh sim in all terminals)
◦ Set the environment/world
◦ Object_grabber nodes
◦ Action client. 
GUANGDONG UNIVERSITY OF TECHNOLOGY - BIRL LAB 18

$ roslaunch baxter_gazebo baxter_world.launch

$ roslaunch exmpl_models add_table_and_coke_can.launch

$ roslaunch baxter_launch_files baxter_object_grabber_nodes.launch

$ rosrun object_grabber example_object_grabber_action_client

The toy block can be reset anytime by running (refer to Sec 3.4):

$ rosrun example_gazebo_set_state reset_block_state
```


## Overview
```
Code Overview of example_object_grabber_action_client.cpp 
main:
set pickup & drop off frames(object_pose, dropoff_pose)
create an action client along with a global alias
move_to_waiting_pose():
create object_grabber_goal with actionCode=MOVE_TO_WAITING_POSE
send action client goal
grab_object(object_pose):
sets action code, object ID, object’s current pose, and grasp strategy.
dropoff_object
similar logic as in grab_object

```

## Structure  --From high level to low level
```
grabber client :robot agnostic plan. Commands approach | grasp |release of object

object_grabber action server : ware of robot, gripper, and object. strategy/plans how to grasp

object manipulation query service : objectManipulationQuery.srv  returns gripper_pose_options[] for specific object & gripper type

generic gripper  service : genericGripperInterfacey.srv  returns commands for specific gripper (open/close suck/release)

cartesian planner action server :  cart_move.action plans/executes cartesian trajectories for specific robot can have generic interface

Trajectory Action  Server   : traj.action interpolates way-points for smooth trajectories

Robot  Controller  : Robot on-board controllers actuate motors
```
## Video --you can see the detailed video explanation in youtube below
```
https://www.youtube.com/watch?v=ZL8SRAqf2u4
```
## FAQ
```
Code examples reside in folders corresponding to chapters.

This entire repository should be cloned to: ~/ros_ws/src (assuming your ros workspace is named "ros_ws" and resides within your home directory).  To do so, navigate to ~/ros_ws/src from a terminal and enter:
`git clone https://github.com/wsnewman/learning_ros_noetic.git`
and also clone the external packages used with:
`git clone -r https://github.com/wsnewman/learning_ros_external_packages_noetic.git`

Then, from a terminal, navigate to ~/ros_ws and compile the code with the command:
`catkin_make`

If you are installing ROS for the first time, see the instructions here:
[installation scripts](//github.com/wsnewman/learning_ros_setup_scripts)

The scripts located at this site automate installation of ROS (consistent with the version and packages used with the learning-ROS code examples).  These scripts also install a variety of useful tools.



```


