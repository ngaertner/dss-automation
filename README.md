# dss-automation

## Overview and Purpose
This script is used to manage, collect, align and integrate FITS files taken with a monochrome astro camera.

It can be used to collect (copy or move) the files taken in multiple imaging sessions from a _\<source_folder>_ into a _\<project_folder>_.
In the project folder the single files put are into a project folder structure (_\<project_folder>/lights/\<filter>_), and a DSS project file  for each filter (_\<project_folder>\_\<filter>.dssfilelist_) will be created or updated in the project folder.
The corresponding darks and flats will be automatically added to the DSS files and groups will be created.
On request also a "Super-Luminance" project file will be created consisting of all R,G,B and L lights.
Afterwards the DSS project files of a project folder can be processed automatically (registration and/or stacking).

All steps can be either performed in one command or separately.

## Prerequesites and Assumptions

To use this script the following prerequesites need to be met:
 - Install the latest version of DeepSkyStacker (DSS)
 - Install Python 3 (https://www.python.org/)
 - Install AstroPy (https://www.astropy.org/)
   pip install astropy
 - Create master darks for the different exposures and master flats for the different filters using DSS
 - Copy "config.json.default" file to "config.json" and customize the settings
 
The script works well under the following assumptions:

 - The source directory contains a the fits files for the different filters
 - The filter can be determined using the filename (pattern "\*\_\<filter>\_\*" )
 
## Execution

Execute the script using python:

```console
python dssautomation
```

Usage:
```console
dssautomation [-h] [-m | -c] [-a] [-l] [-r] [-R] [-s] [-i] [source_dir] project_dir

Positional Arguments:
  source_dir          source directory for copy or move
  project_dir         project directory where fits should be stored

Function Flags:
  -h, --help          show this help message and exit
  -m, --move          move files from source folder to project folder
  -c, --copy          copy files from source folder to project folder
  -a, --add           add files to (existing or new) dsslist file
  -l, --super-l       create a SUPER_L file out of R, G, B, L
  -r, --register      register all non-registered files in dssfiles of project folder
  -R, --register-all  (re-)register all files in dssfiles of project folder
  -s, --stack         (re-)stack all files in dssfiles of project folder
  -i, --intermediate  create registered and calibrated intermediate FITS images while stacking
```
