============
Ubuntu install of ROS Indigo
============
We are building Debian packages for several Ubuntu platforms, listed below.
These packages are more efficient than source-based builds and are our preferred installation method for Ubuntu.

Installation Tutorial:

1. Configure your Ubuntu repositories

Configure your Ubuntu repositories to allow "restricted," "universe," and "multiverse." You can follow the Ubuntu guide for instructions on doing this.

2. Setup your sources.list

Setup your computer to accept software from packages.ros.org. ROS Indigo ONLY supports Saucy (13.10) and Trusty (14.04) for debian packages.
::
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

3. Set up your keys.
::
    sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net --recv-key 0xB01FA116
    
You can try the following command by adding :80 if you have gpg: keyserver timed out error.
::
    sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116

4. Installation.
::
    sudo apt-get update

Desktop-Full Install: (Recommended) : ROS, rqt, rviz, robot-generic libraries, 2D/3D simulators, navigation and 2D/3D perception.
::
    sudo apt-get install ros-indigo-desktop-full

5. Initialize rosdep.

Before you can use ROS, you will need to initialize rosdep.rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS.
::
    sudo rosdep init
    rosdep update

6. Environment setup.

It's convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched.
::
    echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc
    source ~/.bashrc

If you have more than one ROS distribution installed, ~/.bashrc must only source the setup.bash for the version you are currently using. If you just want to change the environment of your current shell, you can type.
::
    source /opt/ros/indigo/setup.bash
    
If you use zsh instead of bash you need to run the following commands to set up your shell.
::
    echo "source /opt/ros/indigo/setup.zsh" >> ~/.zshrc
    source ~/.zshrc
    
7. Getting rosinstall.

rosinstall is a frequently used command-line tool in ROS that is distributed separately. It enables you to easily download many source trees for ROS packages with one command.
To install this tool on Ubuntu, run.
::
    sudo apt-get install python-rosinstall


Now, to test your installation.
