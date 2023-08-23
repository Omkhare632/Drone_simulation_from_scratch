ROS stands for Robot Operating System.  
Despite it's name, it is not an operating system like Windows or Linux. It provides a collection of software libraries, tools and conventions that help developers to create and manage robot behaviours.
For more information you can check out its official site __[Official site](http://wiki.ros.org/noetic)__  

The version of ROS depends upon the version of Ubuntu you are using:  
    For Ubuntu 18.04 : ROS Melodic  
    For Ubuntu 20.04 : ROS Noetic  
    For Ubuntu 22.04 : ROS Humble  

ROS was updated to ROS2 and it is compatible with Ubuntu 22.04. But as both of these are new and not used by many people as of yet, you might face some difficulties.  
Ubuntu 18.04 and 20.04 are compatible with ROS, but Ubuntu 18.04 is a bit more older and less suitable since it has little support for some required files and libraries.  
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
