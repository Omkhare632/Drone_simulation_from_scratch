ROS stands for Robot Operating System.  
Despite it's name, it is not an operating system like Windows or Linux. It provides a collection of software libraries, tools and conventions that help developers to create and manage robot behaviours.
For more information you can check out its official site __[Official site](http://wiki.ros.org/noetic)__  

The version of ROS depends upon the version of Ubuntu you are using:  
    For Ubuntu 18.04 : ROS Melodic  
    For Ubuntu 20.04 : ROS Noetic  
    For Ubuntu 22.04 : ROS Humble

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
