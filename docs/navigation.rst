====================
navigation
====================

On DeepBot:
run :
roslaunch turtlebot_bringup minimal.launch

new terminal:
roslaunch turtlebot_navigation gmapping_demo.launch

On the workstation, open a terminal window and run:

roslaunch turtlebot_rviz_launchers view_navigation.launch

new terminal:
roslaunch turtlebot_teleop keyboard_teleop.launch

please using the keyboard to move around to make the map.

On TurtleBot, open a terminal window and run:

rosrun map_server map_saver -f /tmp/my_map
ls /tmp/

You will now see two files in the /tmp/ directory my_map.pgm and my_map.yaml. As you create maps in the future, you can save them with different names (e.g. /tmp/my_office).

====================
Autonomous Driving
====================

Stop everything from the previous tutorials on both the TurtleBot and the workstation. On TurtleBot run:

roslaunch turtlebot_bringup minimal.launch
roslaunch turtlebot_navigation amcl_demo.launch map_file:=/tmp/my_map.yaml

With everything running successfully on TurtleBot, go to the workstation and run:

roslaunch turtlebot_rviz_launchers view_navigation.launch --screen

// sucessfull test with device robot id : 72.
already map at : //home/ubuntu/turtlebot_custom_maps/mymapdemo.yaml







