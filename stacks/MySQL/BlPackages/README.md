# BladeLogic Package for MySQL

Mimnimum Bladelogic version required for all the packages is 8.5.


## Install overview

Each zip file is a package, to import it in Bladelogic, you first need to unzip the file on a server that has an agent registered in Bladelogic server or on the host of your Bladelogic console.
Some package might require that you put some specific payloads in specific directories before you can import them. This is detailed in this document for each package.

To import a package from the console, right click on the depot folder under which you want to import the BlPackage, then select the import source (the folder resulting of the unzip).

## Provisioning packages

## Management Packages

Those packages are to manage MySQL as executing SQL script, start, stop MySQL.

### Unix

Following packages has been tested on RedHat but may work on other unix flavor with fiew or even no modifications.

#### SQLExecution-Unix

This package is for executing SQL scripts on a MySQL database.

The package can be parameterized with the following properties:
- MYSQL_USER: MySQL user to be used to connect for executing scripts
- MYSQL_PASSWORD: Password of MYSQL_USER
- MYSQL_SERVER: MySQL server name on which to connect. Can be local host if target is the MySQL server
- MYSQL_DATABASE: MySQL databqse name on which the scripts have to be run
- SQL_SCRIPT_PATH: Path to the SQL script or to directory containing SQL scripts. If it is a directory, the scripts are executed in alphabetical order. If path start by . , then path is considered to be relative from DEPLOY_DIR
- DEPLOY_DIR: Staging directory where content may have been deployed in previous stage, can be useless, depend of target and automation cycle.

## Windows

