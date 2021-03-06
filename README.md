# GMTSAR GUI for Sentinel-1 IW data
This python3 program is for reducing time to create batch file for processing Sentinel-1 IW data by GMTSAR.
In Ubuntu, the default python program would be python2; as the result, remember to execute it by python3.  (~$ python3 GMTSAR_S1__v3.py)

There are four tabs for different purposes in the program as followings: 
* Info: choose the directories of S-1 scenes and precise orbit ephemerides; and the paths of DEM file, config file [and s1a-aux-cal.xml]. 
* Step 0: choose the S-1 scenes (from date), and their polarization and sub-swath. 
* Step 1: link the files to raw & topo directories and create data.in and \*.csh for preprocessing step. 
* Step 2: select the day interval for interferometric pairs and it would help automatically create the intf.in file. 

After these steps, 01_prep.csh and 02_proc.csh will be created, and some related files are copied.

Remember to check before you run \*.csh files!

Note!
* If you select the polarization that some scenes don't have, they will be automatically removed.
* If their are some scenes with no precise orbit ephemerides in the directory you provided, please download them before press the <Create> button.

# Create an execute file
pyinstaller --onefile GMTSAR_GUI__v3.py

Details for pyinstaller: https://pyinstaller.readthedocs.io/en/stable/#
