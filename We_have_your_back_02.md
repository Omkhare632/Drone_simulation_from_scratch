sim_vehicle.py giving you a problem?
Don't worry, we have got you.
To make it run, waf is required.

If ardupilot is installed correctly with all the libraries, then waf gets installed automatically.
If that does not happen, it can be installed with:
                sudo apt install waf
U can check if waf is present or not by:
                cd ardupilot
                ls
   This will give a list of all the stuff present in your ardupilot (including waf if present)
   
Once these checks are done, waf needs to be configured. This can be done with:
                ./waf configure --board sitl
               
If it shows permission errors:
                chmod +x waf
               
Configure it again, it should cong=figure without errors

Then u need to do this:
                ./waf copter
               
If all is installed correctly, all the 1124 files will be configured

Then u can run:
                sim_vehicle.py -w
               
If the error is about python then go to ardupilot->Tools->autotest->sim_vehicle.py text file
and edit the 1st line as:
          #!usr/bin/env to #!usr/bin/python3
save it and it should run.

If the same error continues, then go to ardupilot->modules->waf->waf-light
and edit the 1st line as:
          #!usr/bin/env to #!usr/bin/python3
save it and now it should run.
