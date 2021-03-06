# Arista Cloudvision&reg; Portal Configlet Builder Examples
This directory contains a collection of Configlet Builder examples and best practices for
CloudVision&reg; Portal. Each directory should contain an example with a small writeup (README.md)
describing the function.

Each dir should also have the .zip file that was exported so that others can easily upload it into CVP, as well as the txt file with the actual script file itself. This will make it easy for others to edit files.

## Directives
A helper script ('parse_configlet_export.py') has been provided to assist in parsing out the
meat of the Configlet Builders. Example:

Assume we have two Configlet Builders within CVP we would like to share out (CB_example1 and CB_example2).
Navigate to the 'Configlets' section of CVP Portal and select the Configlet Builders you would like to export.
Next click the export icon at the top right of the configlet table.

After the configlet data has been exported from CVP (in our example ExportedConfigletsData.zip)
perform the following steps:

Create an example directory, copy the newly created/downloaded ExportedConfigletsData.zip into the
example directory and chdir into it:
```console
$ mkdir example_directory/
$ cp ExportedConfigletsData.zip example_directory/
$ cd example_directory/
```

Parse the exported configlet data file to extract the Configlet Builders contained:
```console
$ ../parse_configlet_export.py ExportedConfigletsData.zip
$ ls
CB_example1 CB_exmaple2 ExportedConfigletsData.zip
```
Add your README.md file describing the function of your Configlet Builder example.

Commit your example.

## How to Import Configlet Builder templates into CloudVision
To import these templates into CloudVision.

* Download the zip file from one of the example directories
* Click Upload under CloudVision > Configlets > Import > choose zip file.

Examples shipped with cvp-tools (CloudVision) can be added by going to the bash and type
```console
$ cd /cvp/tools
$ ./cvptool.py --host <host> --user <user> --password <pass> --objects Configlets --action restore --tarFile
examples.tar
```

## Examples shipped as part of cvp-tools
* EX0_TestGlobalsBuilder
* EX1_Form_MgmtIntBuilder
* EX2_eAPI_MgmtIntBuilder
* EX3_SSH_MgmtIntBuilder
* EX4_mySQL_MgmtIntBuilder
* EX5_VxlanBuilder

## User provided examples
* free_ports
* servicesDB
* jk
