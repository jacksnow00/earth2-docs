=================
Automatic Docking
=================

1. Deep Learning Robot's battery
--------------------------------
To see the current battery level of the Deep Learning Robot, you can run the following commands::

    roslaunch turtlebot_bringup minimal.launch
    rostopic echo /mobile_base/sensors/core

These commands will print out the various values of the robot's sensors (press *Ctrl + C* to stop the commands).
You can see both the current battery level and whether the robot is charging or not.
For the Deep Learning Robot, the maximum value of battery is 160 and the minimum value is 100.
If the robot is almost out of battery, you should drive it to the nearest docking station and recharge it.

The Deep Learning Robot continuously monitors the battery level and alert the user with an SMS if the battery falls
below a certain threshold.
Therefore, you need to setup your phone number in the robot's environment.
You can check the phone number in current environment by running::

    echo $ROBOTCITY_USER_PHONE_NUMBER

To set the phone number, type in::

    export ROBOTCITY_USER_PHONE_NUMBER=<your-phone-number-here>

The phone number should be in `E.164 format <https://en.wikipedia.org/wiki/E.164>`_:
``[+][country code][subscriber number including area code]``.
For example::

    export ROBOTCITY_USER_PHONE_NUMBER=+841234567890

2. Autodocking Deep Learning Robot
----------------------------------
We provided a convenient launch file for you to autodock the robot.
On the Deep Learning Robot, open a new terminal and type::

    cd ~/
    roslaunch auto_dock/auto_dock.launch

If this script finishes successfully, the robot will be at the docking station and a green light on the robot's base
will blink to notify that it is being charged.
If you manually drive the robot to the docking station, it can be quite difficult to dock the robot correctly.
If the green light is not blinking while the robot is at the docking station, it is not correctly docked.

The autodocking script only works if the Deep Learning Robot is not too far off the docking station.
The working area is about 3x3 meters in front of the docking station.
Also, the path between the docking station and the robot should be clear (the robot doesn't avoid obstacles
while autodocking).

If the distance between the Deep Learning Robot and a docking station is too large or if there are some obstacles along
the way, you need to manually drive the robot closer to the docking station.
You can find more instruction on how to tele-operate your robot in :ref:`navigation`.
When the robot is close enough, you can call the autodocking script and

For more information about the mechanism of the autodocking process, visit `Testing Automatic Docking <http://wiki.ros.org/kobuki/Tutorials/Testing%20Automatic%20Docking>`_
