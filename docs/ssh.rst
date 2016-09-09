============
Setting Up Networking SSH
============
Now that we’ve chased TurtleBot around while pressing keys on the netbook, we can really appreciate the workstation. This allows you to control TurtleBot from the comfort of your chair.

1. Synchronizing Clocks (TurtleBot and Workstation)
---------------
Follow only the “Network Time Protocol” instructions on the Post-Installation Setup page. Skip the special cases instructions.

QUICK TIP:You need config ROUTER NAT PORT to open ssh to your PC from internet. To avoid problems moving forward, disable security options such as firewalls and anything that does port blocking .

2. Set Up Networking (TurtleBot and Workstation)
-------------
Follow the network configuration instructions and follow the options for “source installation”. Note that there are different and specific instructions for TurtleBot and the workstation.

3. Shell into TurtleBot
-----------------
Though you can always go find the TurtleBot and type in the commands directly, it’s more convenient to SSH into its computer and control it from there.
On the workstation, open a terminal and run:
::
  ssh ubuntu@[ip_of_deepbot]
  #password: ubuntu
  
Now you can SSH into TurtleBot to run scripts including the start-up script:
::
  roslaunch turtlebot_bringup minimal.launch

4. Drive in Comfort
------------------
On the TurtleBot computer, close all terminal windows, close the computer, and set it on the second shelf like we did in the Hardware Setup tutorial. Now that you know how to SSH into TurtleBot via your workstation you can run anything you need via the workstation.
  Run:
  ::
    roslaunch turtlebot_bringup minimal.launch
  
  NOTE: turtlebot_bringup is the way of “booting up” TurtleBot. This must be run remotely on TurtleBot, never directly on the workstation.

On the workstation, run:
::
  roslaunch turtlebot_teleop keyboard_teleop.launch
  
  
