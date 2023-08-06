1. If you encounter something like:
```
        error: Your local changes to the following files would be overwritten by checkout:
	Rover/createTags
	Tools/CPUInfo/output-PixFlamingo.txt
	Tools/CodeStyle/ardupilot-astyle.sh
	Tools/FilterTestTool/BiquadFilter.py
	Tools/FilterTestTool/run_filter_test.py
	Tools/Frame_params/Parrot_Disco/gpio.sh
	Tools/Frame_params/Parrot_Disco/rcS_mode_default
	Tools/Frame_params/Parrot_Disco/start_ardupilot.sh
	Tools/IO_Firmware/iofirmware_f103_8MHz_highpolh.bin
	Tools/IO_Firmware/iofirmware_f103_8MHz_lowpolh.bin
	Tools/IO_Firmware/iofirmware_highpolh.bin
	Tools/IO_Firmware/iofirmware_lowpolh.bin
	Tools/Linux_HAL_Essentials/pru/aiopru/start_test
	Tools/Linux_HAL_Essentials/startup.sh
	Tools/LogAnalyzer/LogAnalyzer.py
	Tools/LogAnalyzer/UnitTest.py
	Tools/PrintVersion.py
	Tools/Replay/CheckLogs.py
	Tools/Replay/check_replay.py
	Tools/Replay/check_replay_branch.py
	Tools/UDP_Proxy/start_proxies.sh
	Tools/Vicon/vicon_mavlink.py
	Tools/ardupilotwaf/embed.py
	Tools/autotest/autotest.py
	Tools/autotest/bisect-helper.py
	Tools/autotest/check_autotest_speedup.py
	Tools/autotest/fakepos.py
	Tools/autotest/fg_plane_view.bat
	Tools/autotest/fg_plane_view.sh
	Tools/autotest/fg_quad_view.bat
	Tools/autotest/fg_quad_view.sh
        Tools/autotest/logger_metadata/enum_parse.py
	Tools/autotest/logger_metadata/parse.py
	Tools/autotest/param_metadata/param_parse.py
	Tools/autotest/param_metadata/rstemit.py
	Tools/autotest/run_in_terminal_window.sh
	Tools/autotest/sim_vehicle.py
	Tools/autotest/test_build_options.py
	Tools/autotest/validate_board_list.py
	Tools/autotest/win_sitl/RunCopter.bat
	Tools/autotest/win_sitl/RunPlane.bat
	Tools/autotest/win_sitl/RunRover.bat
	Tools/autotest/win_sitl/UpdateAPMSource.bat
	Tools/bootloaders/AIRLink_bl.bin
	Tools/bootloaders/ARK_GPS_bl.bin
	Tools/bootloaders/ARK_RTK_GPS_bl.bin
	Tools/bootloaders/AeroFox-Airspeed-DLVR_bl.bin
	Tools/bootloaders/AeroFox-Airspeed_bl.bin
	Tools/bootloaders/AeroFox-GNSS_F9P_bl.bin
	Tools/bootloaders/AeroFox-PMU_bl.bin
	Tools/bootloaders/AtomRCF405NAVI_bl.bin
	Tools/bootloaders/BeastF7v2_bl.bin
	Tools/bootloaders/BeastH7_bl.bin
	Tools/bootloaders/BeastH7v2_bl.bin
	Tools/bootloaders/BirdCANdy_bl.bin
	Tools/bootloaders/BirdCANdy_bl.elf
	Tools/bootloaders/C-RTK2-HP_bl.bin
	Tools/bootloaders/CUAV-Nora_bl.bin
	Tools/bootloaders/CUAV-Nora_bl.elf
	Tools/bootloaders/CUAV-X7_bl.bin
	Tools/bootloaders/CUAV-X7_bl.elf
	Tools/bootloaders/CUAV_GPS_bl.bin
        Tools/bootloaders/CUAV_GPS_bl.elf
	Tools/bootloaders/CUAVv5-bdshot_bl.bin
	Tools/bootloaders/CUAVv5Nano-bdshot_bl.bin
	Tools/bootloaders/CUAVv5Nano_bl.bin
	Tools/bootloaders/CUAVv5Nano_bl.elf
	Tools/bootloaders/CUAVv5_bl.bin
	Tools/bootloaders/CUAVv5_bl.elf
	Tools/bootloaders/CubeBlack+_bl.bin
	Tools/bootloaders/CubeBlack_bl.bin
	Tools/bootloaders/CubeBlack_bl.elf
	Tools/bootloaders/CubeGreen-solo_bl.bin
	Tools/bootloaders/CubeOrange-ODID_bl.bin
	Tools/bootloaders/CubeOrange-bdshot_bl.bin
	Tools/bootloaders/CubeOrange-bdshot_bl.hex
	Tools/bootloaders/CubeOrange-joey_bl.bin
	Tools/bootloaders/CubeOrange-periph-heavy_bl.bin
	Tools/bootloaders/CubeOrange-periph_bl.bin
	Tools/bootloaders/CubeOrange-periph_bl.hex
	Tools/bootloaders/CubeOrangePlus-bdshot_bl.bin
	Tools/bootloaders/CubeOrangePlus_bl.bin
	Tools/bootloaders/CubeOrangePlus_bl.elf
	Tools/bootloaders/CubeOrange_bl.bin
	Tools/bootloaders/CubeOrange_bl.elf
	Tools/bootloaders/CubePurple_bl.bin
	Tools/bootloaders/CubeRedPrimary_bl.bin
	Tools/bootloaders/CubeRedSecondary_bl.bin
	Tools/bootloaders/CubeSolo_bl.bin
        Tools/bootloaders/CubeYellow-bdshot_bl.bin
	Tools/bootloaders/CubeYellow_bl.bin
	Tools/bootloaders/CubeYellow_bl.elf
	Tools/bootloaders/DrotekP3Pro_bl.bin
	Tools/bootloaders/Durandal_bl.bin
	Tools/bootloaders/Durandal_bl.elf
	Tools/bootloaders/F35Lightning_bl.bin
	Tools/bootloaders/F35Lightning_bl.elf
	Tools/bootloaders/F4BY_bl.bin
	Tools/bootloaders/F4BY_bl.elf
	Tools/bootloaders/FlyingMoonF407_bl.bin
	Tools/bootloaders/FlyingMoonF427_bl.bin
	Tools/bootloaders/FlyingMoonH743_bl.bin
	Tools/bootloaders/FlywooF745Nano_bl.bin
	Tools/bootloaders/FreeflyRTK_bl.bin
	Tools/bootloaders/FreeflyRTK_bl.elf
	Tool
        Aborting
```
While running ```git checkout Copter-3.6```
Do not worry!
This might seem a really big error but is actually quite simple to solve, just run:
```
git stash
```
This should work, try running the the command again.
The reason you might get this error is because you might have made changes in certain files and are trying to change branches, so this stashes the files and solves the problem.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
2.  ```fatal: clone of 'git://github.com/UAVCAN/libuavcan.git' ``` into submodule path or a similar error for ```git submodule update --init --recursive``` then run the following command: 
```
git config --global url."https://".insteadOf git://
```
And then re-run the git submodule update command, it should run without any errors.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
3. If you are using Ubuntu 22.04 the you might encounter error like Package ```'python3-wxgtk4.0' has no installation candidate```
   To solve this just change:
```
 sudo apt install python3-wxgtk3.0-0
```
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
4. ```E:Package 'package_name' has no installation candidates```
this messsage occurs because your installer is unable to find the package with mentioned name, check for spelling and remember its case sensitive or it may happen that mentioned version of package is not compitible with your current OS version, you can check the availability of package:
```
sudo apt search package_name
```
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
5. If packages are not available for the system but you still need it, you can install it manually but it has several risks, so this path is not recomanded as it may make generate system errors.
> Note:
> > You can get packages that are used in lower versions of OS but dont install versions that only have supports for higher OS versions in a lower OS version, check compatibility first  


  First __[search and download packages from here]()__   
  Use the `cd` command to navigate to the folder where you downloaded the .deb package. For example, if you downloaded the package to your Downloads folder, you'd use:
  ```
  cd ~/Downloads
  ```
  Use the dpkg command to install the downloaded package. Replace package-name.deb with the actual name of the package file.
```
sudo dpkg -i package-name.deb
```
  If the package has dependencies that are not satisfied, you might see an error. In that case, you can use the following command to fix missing dependencies:
```
sudo apt-get install -f
```
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
