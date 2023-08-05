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
> Encountered an error in above code ?  
> __[We have your back ](https://github.com)__
#### Dependencies for Ardupilot
```
sudo apt install python3-matplotlib python3-serial python3-wxgtk4.0 python3-lxml python3-scipy python3-opencv ccache gawk python3-pip python-pexpect
```
for further process you will need to install pip installer
```
sudo apt install python3-pip
```
### Install Mavproxy
MAVProxy is a fully-functioning GCS for UAV’s, designed as a minimalist, portable and extendable GCS for any autonomous system supporting the MAVLink protocol (such as one using ArduPilot). 
Read more about it at its __[official page](https://ardupilot.org/mavproxy/)__
We need to 
