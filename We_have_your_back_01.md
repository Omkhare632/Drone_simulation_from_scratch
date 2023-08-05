####Error:
##fatal: clone of 'git://github.com/UAVCAN/libuavcan.git' into submodule path
for ```git submodule update --init --recursive``` then run the following command: 
```
git config --global url."https://".insteadOf git://
```
And then re-run the git submodule update command, it should run without any errors.
