ROS stands for Robot Operating System.  
Despite it's name, it is not an operating system like Windows or Linux. It provides a collection of software libraries, tools and conventions that help developers to create and manage robot behaviours.
For more information you can check out its official site __[Official site](http://wiki.ros.org/noetic)__  

The version of ROS depends upon the version of Ubuntu you are using:  
    For Ubuntu 18.04 : ROS Melodic  
    For Ubuntu 20.04 : ROS Noetic  
    For Ubuntu 22.04 : ROS Humble  

ROS was updated to ROS2 and it is compatible with Ubuntu 22.04. But as both of these are new and not used by many people as of yet, you might face some difficulties.  
Ubuntu 18.04 and 20.04 are compatible with ROS, but Ubuntu 18.04 is a bit more older and less suitable since it has little support for some required files and libraries and python3.  
Ubuntu 20.04 is the right version as it is not too old nor too new and you will find projects and solutions to problems easily for Ubuntu 20.04 and ROS.

## Installing ROS:

1. We need to setup our computer to accept the software from packages.ros.org
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

2. We need to set up our keys:
```
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```
  
3. We are ready to install ROS:  
Update the Debian package:
```
sudo apt update
```
Installing ros:
```
sudo apt install ros-noetic-desktop-full
```
This is for Ubuntu 20.04, for other versions replace ```noetic``` with appropriate ros version (melodic, humble, etc)  
   
4. Now that ROS is installed, we need to set up our environment:
```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```  
This is for Ubuntu 20.04, for other versions replace ```noetic``` with appropriate ros version (melodic, humble, etc)  

5. Install the required dependencies:
We have installed the core ros packages, now we need to install tools that will help us to create and manage our own workspaces.
```
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```
This is for Ubuntu 20.04 and higher versions, for other versions replace ```python3``` with ```python```  

6. Initializing rosdep
rosdep enables you to use some core ROS libraries, also makes it easier to install the required dependencies.
```
sudo apt install python3-rosdep
sudo rosdep init
rosdep update
```
This is for Ubuntu 20.04 and higher versions, for other versions replace ```python3``` with ```python``` 

## Setting up our workspace  
We use ```catkin build``` instead of ```catkin_make```
Install the following:
```
sudo apt-get install python3-wstool python3-rosinstall-generator python3-catkin-lint python3-pip python3-catkin-tools
pip3 install osrf-pycommon
```
This is for Ubuntu 20.04 and higher versions, for 18.04:
```
sudo apt-get install python-wstool python-rosinstall-generator python-catkin-tools
```
Initialixing the workspace:
```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin init
```

## Installing mavros and mavlink  
