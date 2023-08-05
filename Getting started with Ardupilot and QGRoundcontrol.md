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
