====================
Testing Camera 3D
====================

1. Script run On Deep Learning RoBot.
---------------
first terminal.
::
  roslaunch turtlebot_bringup minimal.launch

second terminal.
::
  roslaunch openni2_launch openni2.launch

2. View Image Data (Workstation)
----------------
Close all terminal windows, open a new one, and run:
::
  rosrun rqt_image_view rqt_image_view
  
You can select image topic to view.
