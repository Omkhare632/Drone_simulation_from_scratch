## Getting started with Ardupilot and QGroundcontrol  
Getting Ardupilot Repository Clone:   
```
cd ~
sudo apt update
sudo apt upgrade
sudo apt install git
```
###### Note:
> We recomand to  download the Ardupilot reposiotry that we have uploaded just because we have used it from start to end of our project and it has all required files already present but you can also go with official Ardupilot resposiotory download that we ahve provided the the link in the below code.
>> To start with our Ardupilot repository use this:
>> __[Full Ardupilot Setup Repository](https://github.com)__
.after this skip the ardupilot clonning step below and follow all others.

```
git clone https://github.com/ArduPilot/ardupilot.git
cd ardupilot
git checkout Copter-3.6
git submodule update --init --recursive
```
> Encountered an error in the above code ?  
> __[We have your back ](https://github.com)__

#### Dependencies for Ardupilot
```
sudo apt install python3-matplotlib python3-serial python3-wxgtk4.0 python3-lxml python3-scipy python3-opencv ccache gawk python3-pip python-pexpect
```
> Encountered an error in the above code ?  
> __[We have your back ](https://github.com/Omkhare632/Drone_simulation_from_scratch/blob/5e102dfe49cd2925592097784eb9dea140c26718/We_have_your_back_01.md#L120)__

If you are using Ubuntu 22.04, these are some additional dependencies you need to install:
```
sudo apt update
sudo apt install git python3-dev python3-tk
sudo apt install gawk cpp g++ gcc git gfortran make wget xz-utils
sudo apt install python3-pyside2.qtopengl python3-pyside2.qtwebengine python3-pyside2.qtsvg
sudo apt install python3-opencv python3-numpy python3-scipy python3-pygame
```

### Install Mavproxy
MAVProxy is a fully-functioning GCS for UAV’s, designed as a minimalist, portable and extendable GCS for any autonomous system supporting the MAVLink protocol (such as one using ArduPilot). 
Read more about it at its __[official page](https://ardupilot.org/mavproxy/)__
The command to install MavProxy:
```
pip3 install MAVProxy
```

The `.bashrc` needs to be edited:
It can be opened using two methods: 
```
nano ~/.bashrc
```
or
```
gedit ~/.bashrc
```
Click here to __[know more about bashrc](https://github.com)__

Once you have opened the .bashrc file, add the following lines at the end of file:
```
export PATH=$PATH:$HOME/ardupilot/Tools/autotest
export PATH=/usr/lib/ccache:$PATH
```
To save the file in `nano` command, press `ctrl+x` and when asked to update to buffer press `y` and click `ENTER`  
To save file in`gedit` command, press `ctrl+s` or click on the `save` button on the top right and `exit`

To reload the `.bashrc` file, run the following command:
```
. ~/.bashrc
```
## Software In The Loop
SITL (Software-In-The-Loop) is a simulation method for drones where flight control software is emulated on a computer. It allows testing, training, and software development without physical hardware. SITL interacts with external tools, providing a safe environment for experimenting with drone behaviors and algorithms. It's valuable for rapid iteration and system integration.
you will come to learn use of SITL as we move on in the project.
```
cd ~/ardupilot/ArduCopter
sim_vehicle.py -w
```
> Encountered an error in the above code ?  
> __[We have your back](https://github.com/Omkhare632/Drone_simulation_from_scratch/blob/5da6f59858ab468ed9843a44e8a9277ff316d82d/We_have_your_back_02.md#L50 "solution can be here")__
> 
Here we are done with Ardupilot Setup :wink:
### Setting up QGroundControl 
The devices that use serial communication require direct communication over serial ports which requires access, the ```dialout``` group provides such access.
Modemanager in the dialout group may try communication on its own, which can cause issues, so it needs to be removed.
To create an account on dialout and remove modemanager, run the following commands:
```
sudo usermod -a -G dialout $USER
sudo apt-get remove modemmanager
```
To download QGroundControl, run the following command:
```
wget https://s3-us-west-2.amazonaws.com/qgroundcontrol/latest/QGroundControl.AppImage
```
To change the permissions, run the following commands:
```
chmod +x ./QGroundControl.AppImage
```
AppImages require FUSE (Filesystem in Userspace) to run. It is a kernel module, it allows users to make changes in the file as well as create their own file without modifying the system's kernel code. To install fuse run the following command:
```
sudo apt-get install fuse
```
To load the fuse kernel run the following command:
```
sudo modprobe fuse
```
Now, your QGroundControl is ready to be executed. You can run it with the help of the following command:
``` 
./QGroundControl.AppImage
```
### Running QGroundControl with SITL
Open a different terminal and run the following commands:
```
cd ~/ardupilot/ArduCopter/
sim_vehicle.py
```
