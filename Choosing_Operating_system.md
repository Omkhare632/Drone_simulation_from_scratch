## Choose your Operating System
Its better to always use a Virtual machine if you are not use to the suggested operating system, if you are use to with linux then go for dual boot, check out why and how to on both topics **here**  
We have tried 18.04, 20.04 and 22.04 for this simulation, methods and issues for all are mentioned here  
We will be starting with getting Ardupilot repository then getting QGroundcontrol station,  later Gazebo simualtor and finally ROS.  
Strating the discussion with ubuntu 18.04 and 20.04   

Getting Ardupilot Repository Clone:  
```
cd ~
sudo apt install git
```
Note  
> We recomand to  download the Ardupilot reposiotry that we have uploaded just because we have used it from start to end of our project and it has all required files already present but you can also go with official Ardupilot resposiotory download that we ahve provided the the link in the below code.

```
git clone https://github.com/ArduPilot/ardupilot.git
cd ardupilot
git checkout Copter-3.6
git submodule update --init --recursive
```
