============
Network Configuration
============

Turtlebot Setup
  On the Deepbot we already setup turlebot ROS-Master:

    $ echo export ROS_MASTER_URI=http://localhost:11311 >> ~/.bashrc
    $ echo export ROS_HOSTNAME=IP_OF_DEEPBOT >> ~/.bashrc

  On Your Remote PC Setup
    You should export the variables inside your workspace setup script. Note that the meaning of the ROS_MASTER_URI changes here - the master is in the turtlebot!

    $ echo export ROS_MASTER_URI=http://IP_OF_DEEPBOT:11311 >> ~/.bashrc
    $ echo export ROS_HOSTNAME=IP_OF_PC >> ~/.bashrc


Verify from Remote PC to TurtleBot

  Open a new command line terminal on remote pc and run:

    $ rostopic list
