# dss-automation

copy *.fit files from single folder into project folder

command line input:
 - source directory
 - project directory
 - modeflag
   -c --copy
   -a --add (to project)
   -r --register
   -R --register all
   -s --stack

Execution:

## Copy (c)
Search for "\_x\_*.fit" pattern in file source directory
and put files into corresponding subfolder in project directory.
Add files to corresponding project file (pattern: project \<folder name\>_\<filter\>.txt or .dssfilelist).
If project file is not existing create new file from template.

## Add (a)
Add all fits files of filter folder to "LIGHTS" section of project file.

## Register (r) / Register all (R)
Register ungregistered files of project or register ALL files of project

## Stack
Stack all registered files of project

