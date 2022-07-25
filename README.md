# TravelModel
To run the trip-based travel demand model and process data requests for CLMPO

## Computer set-up
Install EMME, Cygwin, R, and Python 2.7, and set up the environmental variables.

1. EMME (version 4.4.4.2) installer is saved at IS standard folder for installers and a copy in T Drive (T:\Models\EMME), the authorization file requires INRO credentials, which is provided by ODOT;
2. Set up the Cygwin bash file - C:\cygwin64\etc\bash.bashrc, and C:\cygwin64\etc\fstab (replace the last line with "none /cygdrive cygdrive binary,noacl,posix=0,user 0 0");
3. R (version 3.6.1) requires some package installations - installPackages_LCOG.R and installPackages.R saved at T:\Models\KateModel\Metro\misc (mrio_0.1.3.zip needs to be installed from a local drive), all of the packages should be installed at the global folder in C Drive;
4. Install Python 2.7 and copy the site-packages folder from Metro;

## Model running
1. Kate v1.0 cookbook

Model setup - Need to change the seedbank path if run with seed.

1.1 Navigate to the root directory of the iteration

`cd T:/Models/KateModel/Metro/training_runs/iter8`, shortcut --- t

1.2 Make a copy of the Python setup script

`cp T:/Models/KateModel/Metro/programs_v1.0_LCOG_120120/src/py/model_setup_kate1.0.py ./`

1.3 Run the script

`python model_setup_kate1.0.py`

## Data requests
### Lane miles by federal functional class

The federal functional class values are from the Lane County Road Centerlines (RLIDGeo.DBO.Road). Using [the nearest spatial join](https://github.com/dongmeic/TravelModel/blob/main/data_requests/lane_miles/add_functional_classes.ipynb) approach, the federal functional classes are added to the base year 2020 and future year 2045 links. The added variables 'fed_class', 'distances', and 'miles' are 'the federal functional class of the nearest road', 'distances to the nearest road', and 'lane miles of the link segment'. Then lane miles in the base year 2020 and future year 2045 links are [summarized by federal functional classes](https://github.com/dongmeic/TravelModel/blob/main/data_requests/lane_miles/aggregate_lane_miles.ipynb). 
