# BladeLogic Package for Tomcat

Mimnimum Bladelogic version required for all the packages is 8.5.

All the packages have been tested with the following tomcat versions:
1. v7.x

## Install overview

Each zip file is a package, to import it in Bladelogic, you first need to unzip the file on a server that has an agent registered in Bladelogic server or on the host of your Bladelogic console.
Some package might require that you put some specific payloads in specific directories before you can import them. This is detailed in this document for each package.

To import a package from the console, right click on the depot folder under which you want to import the BlPackage, then select the import source (the folder resulting of the unzip).

## Provisioning packages

Those packages are for provisioning tomcat binaries and service instances.

### Linux

Following packages has been tested on RedHat but may work on other unix flavor with few modifications.

#### DeployBinaries-Linux

This package is to deploy the tomcat binaries to a Linux OS.

To import it in Bladelogic, after you've unzipped the file, you need to add the tomcat 7 payload, the tar.gz core, that you got from http://tomcat.apache.org/download-70.cgi in the directory DeployBinaries-Linux/files/blpackages/ba56aea9-358b-4077-8cd5-9f418fee034c/89.1 and rename the file as apache-tomcat.tar.gz.
If for example you downloaded the build 54 of version 7, so you got file apache-tomcat-7.0.54.tar.gz, you need to copy this file in the directory but renamed apache-tomcat.tar.gz
After the payload has been propertly put in the right place, you can import the package.

The package can be parameterized with the following properties:
- TOMCAT_INSTALL_DIR: Installation path where tomcat binaries will be installed (default value: /opt/tomcat7)
- TOMCAT_GID: Group id of system group tomcat that will be created (default value: 501)

On top of binary deployment, the package will also create a folder $TOMCAT_INSTALL_DIR/instances with full right for tomcat group. This folder can be use as root for instance folders of tomcat instance that can be created using CreateInstance-Linux.

#### CreatInstance-Linux

This package is to create and start tomcat a tomcat instance owned by a non root user part of tomcat group. 

To import the package, you just need to unzip it and import it from the console as decribed in the install overview chapter.

The package can be parameterized with the following properties:
- TOMCAT_INSTALL_DIR: Installation path where tomcat binaries are installed (default value: /opt/tomcat7). Typically, binaries may have been installed using DeployBinaries-Linux package
- JAVA_HOME: Root directory of the java jdk to use with tomcat (default value: /usr/java/jdk1.7.0_13)
- TOMCAT_INSTANCE_NAME: Logical name of the instance used for service script that will be named tomcat$TOMCAT_INSTANCE_NAME
- TOMCAT_HOME: Home directory of the instance that will be created (default value: ??TOMCAT_INSTALL_DIR??/instances/??TOMCAT_INSTANCE_NAME??)
- TOMCAT_USER_OWNER: system user owning the tomcat instance server process (default value: tomcat)
- TOMCAT_OWNER_UID: user id of system user specified in TOMCAT_USER_OWNER (default value: 1100)
- TOMCAT_PORT: This is the port where Apache Tomcat listen for the HTTP requests (default value: 8180)
- TOMCAT_REDIRECT_PORT: Any redirection happening inside Apache Tomcat will happen through this port (default value: 8543)
- TOMCAT_SHDOWN_PORT: This port is used when we try to shutdown the Apache Tomcat Server instance (default value: 8105)
- TOMCAT_AJP_PORT: The Apache JServ Protocol (AJP) is a binary protocol that can conduct inbound requests from a web server through to an application server that sits behind the web server (default value: 8109)
- TOMCAT_USER: Tomcat user with management right and deployment right (default value: tomcat)
- TOMCAT_PASSWORD: Password of the tomcat user defined in TOMCAT_USER property (default value: password)
- TOMCAT_START: Package deployment starts the tomcat instance if set to true else doesn't start it (default value: true)

### Windows


## Management Packages

Those packages are to manage tomcat instances as application deployment, undeploy application, start and stop instances.

### Linux

Following packages has been tested on RedHat but may work on other unix flavor with fiew or even no modifications.

### Windows

