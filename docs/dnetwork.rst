============
Network Configuration
============

1. Setup on Deep Learning Robot.
-----------------
On the Deepbot we already setup turlebot ROS-Master.
::
  echo export ROS_MASTER_URI=http://localhost:11311 >> ~/.bashrc
  echo export ROS_HOSTNAME=IP_OF_DEEPLEARNINGROBOT >> ~/.bashrc

2. Setup on Your Remote PC.
-------------------
You should export the variables inside your workspace setup script. Note that the meaning of the ROS_MASTER_URI changes here the master is in the turtlebot!
::
  echo export ROS_MASTER_URI=http://IP_OF_DEEPLEARNINGROBOT:11311 >> ~/.bashrc
  echo export ROS_HOSTNAME=IP_OF_YOUR_ROUTER_PC >> ~/.bashrc

3. Verify from Remote PC to Deep Learning Robot.
---------------------
Open a new command line terminal on remote pc and run:
::
  rostopic list
