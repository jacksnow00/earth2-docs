.. _navigation:

==========
Navigation
==========

1. Script run On Deep Learning RoBot.
-------------------------------------
first terminal.
::
  roslaunch turtlebot_bringup minimal.launch

second terminal.
::
  roslaunch turtlebot_navigation gmapping_demo.launch

2. Script run on Your PC workstation.
-------------------------------------
first terminal.
::
  roslaunch turtlebot_rviz_launchers view_navigation.launch
  
second terminal.
::
  roslaunch turtlebot_teleop keyboard_teleop.launch

3. Make the map.
----------------
please using the keyboard to move around to make the map. On Deep Learning Robot.
open a terminal window and run:
::
  rosrun map_server map_saver -f /tmp/my_map
  ls /tmp/
  
You will now see two files in the /tmp/ directory my_map.pgm and my_map.yaml. As you create maps in the future, you can save them with different names (e.g. /tmp/my_office).

==================
Autonomous Driving
==================

1. Load the map.
----------------
Stop everything from the previous tutorials on both the  Deep Learning Robot and the workstation.
On  Deep Learning Robot run:
::
  roslaunch turtlebot_bringup minimal.launch
  roslaunch turtlebot_navigation amcl_demo.launch map_file:=/tmp/my_map.yaml

With everything running successfully on Deep Learning Robot, go to the workstation and run:
::
  roslaunch turtlebot_rviz_launchers view_navigation.launch --screen


