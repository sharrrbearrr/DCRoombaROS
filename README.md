# DCRoombaROS

This a project built on a Raaspberry Pi running Ubuntu using ROS Kinetic software .

# Step 1
Download the reccomended ROS Kinetic software following the instructions in the link below. Make sure to follow the Desktop Full Reccommended Install.

# Step 2

Create the workspace and nodes following these commands.They are taken from the link below:

https://www.intorobotics.com/ros-kinetic-publisher-and-subscriber-in-python/

4.1 The commands to create the workspace
mkdir -p ~/your_workspace_name_here/src 
cd ~/ your_workspace_name_here/src
catkin_init_workspace
catkin_make
source devel/setup.bash

The above commands create a set of directories that will host all ROS nodes.

If the first two commands should be familiar, the following two commands are ROS-specific. Both commands are designed to create meta data for ROS. The “catkin_init_workspace” command creates the CmakeLists.txt file. The “catkin_make” command generates a series of directories to host files, libraries, or executable programs.

4.2 Commands for creating the ROS package

It is necessary that the ROS package containing the two nodes to be included in the workspace directory. In addition, each package will contain two files: CmakeLists.txt and package.xml.

The commands for creating the package are:

cd ~/your_workspace_name_here/src
catkin_create_pkg your_package_name rospy
‘catkin_create_pkg’ is the command for creating the new package.
‘rospy’ is the dependency of the new package created by the rospy package.

# Step 3

Save the attached code in text files using the echo commands, while in the workspace.

# Step 4
In three different terminal windows run following command

Terminal 1 [run roscore]:
export ROS_MASTER_URI=http://[pi_ip_address]:11311
export ROS_IP=[pi_ip_address]
roscore

Terminal 2 [run roslaunch driver]:
export ROS_MASTER_URI=http://[pi_ip_address]:11311
export ROS_IP=[pi_ip_address]
cd ~/irobot/
source develop/setup.bash
roslaunch ca_driver  create_2.launch

Terminal 3 [run keyboard, press k or l to rotate the roomba]:
export ROS_MASTER_URI=http://[pi_ip_address]:11311
export ROS_IP=[pi_ip_address]
cd ~/irobot/
source develop/setup.bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py 


Please Note
In addition, you can find all ros packages available by typing
rospack list


# Step 5
Power the Raspberry Pi with a battery pack and connect the serial cable to the Pi and the Roomba.


