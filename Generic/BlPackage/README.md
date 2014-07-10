# BladeLogic Package for various actions

Mimnimum Bladelogic version required for all the packages is 8.5.


## Install overview

Each zip file is a package, to import it in Bladelogic, you first need to unzip the file on a server that has an agent registered in Bladelogic server or on the host of your Bladelogic console.
Some package might require that you put some specific payloads in specific directories before you can import them. This is detailed in this document for each package.

To import a package from the console, right click on the depot folder under which you want to import the BlPackage, then select the import source (the folder resulting of the unzip).


## Unix

Following packages has been tested on RedHat but may work on other unix flavor with fiew or even no modifications.

### CopyFileDir-Unix

This package is for copying a file or a directory to a targeted location on the same target.

The package can be parameterized with the following properties:
- SOURCE: File or directory source to copy. If path start by . , then path is considered to be relative from DEPLOY_DIR
- DESTINATION: Destination to copy the file or the diectory. If path start by . , then path is considered to be relative from DEPLOY_DIR
- DEPLOY_DIR: Staging directory where content may have been deployed in previous stage, can be useless, depend of target and automation cycle.

### RemoveFileDir-Unix

This package is for deleting files or directory from the target.

The package can be parameterized with the following properties:
- FILES: List of files, directories to remove (separated by space). If path start by . , then path is considered to be relative from DEPLOY_DIR
- DEPLOY_DIR: Staging directory where content may have been deployed in previous stage, can be useless, depend of target and automation cycle.

## Windows

