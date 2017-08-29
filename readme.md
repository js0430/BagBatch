BagBatch: BagIt batch processing in Python
================================
Version 1.1.5  
Updated August 29, 2017  

[__BagIt and bagbatch.py__](https://github.com/js0430/BagBatch#bagit-and-bagbatchpy)  
[__Requirements and setup__](https://github.com/js0430/BagBatch#requirements-and-setup)  
– [BagIt](https://github.com/js0430/BagBatch#bagit)  
– [Java](https://github.com/js0430/BagBatch#java)  
– – – [Setting up the JAVA\_HOME environment variable](https://github.com/js0430/BagBatch#setting-up-the-java_home-environment-variable)  
– – – – – – – [Windows 7](https://github.com/js0430/BagBatch#windows-7)  
– – – – – – – [Windows 10](https://github.com/js0430/BagBatch#windows-10)  
– [Python](https://github.com/js0430/BagBatch#python)  
– – – [Installation Details: Windows 7](https://github.com/js0430/BagBatch#installation-details-windows-7)  
– – – [Installation Details: Windows 10](https://github.com/js0430/BagBatch#installation-details-windows-10) 
– [Opening Command Prompt](https://github.com/js0430/BagBatch#opening-command-prompt) 
– – – [Windows 7](https://github.com/js0430/BagBatch#windows-7-1)  
– – – [Windows 10](https://github.com/js0430/BagBatch#windows-10-1)
[__Using bagbatch.py__](https://github.com/js0430/BagBatch#using-bagbatchpy)  
– [Overview](https://github.com/js0430/BagBatch#overview)  
– [Usage](https://github.com/js0430/BagBatch#usage)  
– [Detailed Instructions](https://github.com/js0430/BagBatch#detailed-instructions)  
[__Setting up a new version of BagIt or changing the installation path__](https://github.com/js0430/BagBatch#setting-up-a-new-version-of-bagit-or-changing-the-installation-path)  
– [Overview](https://github.com/js0430/BagBatch#overview-1)  
– [Detailed Instructions](https://github.com/js0430/BagBatch#detailed-instructions-1)  
[__Troubleshooting__](https://github.com/js0430/BagBatch#troubleshooting)  
– [Java](https://github.com/js0430/BagBatch#java-1)  
– [Python](https://github.com/js0430/BagBatch#python-1)  
– [Bagit](https://github.com/js0430/BagBatch#bagit-1)  
– [BagBatch](https://github.com/js0430/BagBatch#bagbatch)  

## BagIt and bagbatch.py

BagIt is a Java-based program that creates archival bags of files following the [BagIt standard](https://tools.ietf.org/html/draft-kunze-bagit-14)  developed by the Library of Congress. It is used to store a directory's master copies, web copies, and metadata, or to verify that files have been transferred from one computer to another properly. By default, BagIt only processes one directory at a time. bagbatch.py was written by the [CarletonArchives](https://github.com/CarletonArchives/BagBatch) to process an entire parent directory with folders ready for bagging on both Mac and Windows. 

Version 1.1.4.1 includes a few changes to make it work on Windows 7 or 10 with Python 3.6. If you are running Python 2.x, or you are using Mac OS, please refer to the [original BagBatch project](https://github.com/CarletonArchives/BagBatch). 

## Requirements and setup
 - Windows 7 or Windows 10
 - BagIt
 - Java 8
 - Python 3.6

Follow the instructions below to setup the required programs. For additional information, check out [Carlpedia - BagIt](https://wiki.carleton.edu/display/carl/BagIt), which has links to tutorials and examples.  

If you have an older version of Windows or you are using a Mac, the directions below may not apply to your operating system.  Please note that the instructions for Mac OS have been removed from this fork since there was no opportunity to verify the instructions for Mac OS. 

### BagIt

BagIt can be downloaded from the [Library of Congress on GitHub](https://github.com/LibraryOfCongress/bagit-java/releases/tag/bagit-4.9.0). Adapted from the readme file for BagIt 4.9.0 (see the link above for the most recent information):

 - Unzip bagit-java-master. From this new folder, unzip bagit-x.x.x-src.zip. In the resulting 'bagit-x.x.x/bin' subdirectory, you will find a bag.bat (Windows) script that is used to invoke the command line interface.

Note that the Libary of Congress no longer uses Bagit 4 and has moved to a new version of Bagit that is not compliant with the CarletonArchives BagBatch script.  In the Fall of 2017 CarletonArchives will begin working on updating BagBatch to be compliant with the new version of Bagit, but in the meantime, BagIt 4.9 is still available at https://github.com/LibraryOfCongress/bagit-java/releases/tag/bagit-4.9.0 

### Java

Java must be installed. To check if Java is installed, type `java -version` 
in [Command Prompt](https://github.com/js0430/BagBatch#opening-command-prompt-windows). If Java is not installed, download it from [java.com](https://www.java.com/). Although the BagIt specifications recommend Java 6, bagbatch.py has also been tested with Java 7 and Java 8. If you run into any Java issues, check out the [troubleshooting section](https://github.com/js0430/BagBatch#troubleshooting).

##### Setting up the JAVA_HOME environment variable
The Java runtime environment (JAVA_HOME) must be set up correctly for BagIt to run. Follow the steps for your operating system below.  

###### Windows 7   
1. Click Start/Control Panel. Enter into the search bar 'environment variable' and select *Edit environment variables for your account*. Or, to do it manually: Start/Control Panel/System and Security/System/Advanced system settings/Environment variables.  
2. In the Environment Variables window, under *System variables*, check that a variable named JAVA_HOME exists. If so, the variable is already set up. If not, continue with step 3.  
3. Keeping those windows open, click Start/Control Panel and search for 'Java'. If nothing is found, Java has not been installed correctly. In the Java Control Panel, select the Java tab and then *view*. Under path, copy all but the \bin\javaw.exe part at the end of the path. It should look similar to C:\Program Files\Java\jre7.  
4. Back in the Environment Variables window, create a new system variable with the name JAVA_HOME and with the copied path as the value. Click Ok 

###### Windows 10   
1. Click the Search Windows icon. Enter into the search bar 'environment variable' and select *Edit the system environment variables*.  This will open the *System Properties* window with the *Advanced* tab on top. Click on *Environment Variables...* at the bottom of the *Advanced* tab.
2. In the Environment Variables window, under *System variables*, check that a variable named JAVA_HOME exists. If so, the variable is already set up. If not, continue with step 3.  
3. Click "New...". In the new window, use the Variable name JAVA_HOME. Then click on 'Browse Directory'. The goal is to navigate to the directory where \bin\javaw.exe is stored. The path typically is "This PC", then "Local Disc" (which is usually C:\), then "Program Files", then "Java", then a folder that starts with "jre...". Stop there and click OK.
4. This should create a Variable Value that looks similar to C:\Program Files\Java\jre1.8.0_144.  (The exact numbers after jre1.8 may differ on your computer.)
5. Click OK. 

### Python

This fork uses Python 3.6 to run bagbatch.py.
Enter `python` into [Command Prompt](https://github.com/js0430/BagBatch#opening-command-prompt) to see if Python is setup for command line use. If not, make sure Python is installed (if it isn't, download version 3.6 from python.org). [Python 3.6 documentation for setting up the interpreter](https://docs.python.org/3/tutorial/interpreter.html). 

###### Installation Details: Windows 7
Python must be able to run from Command Prompt. The Python environment variable must be created, similar to how the JAVA_HOME variable was setup.  

1. Find the installation folder for Python 3.6, which is usually C:\Python.  
2. Click Start/Control Panel. Enter into the search bar 'environment variable' and select *Edit environment variables for your account*. Or, to do it manually: Start/Control Panel/System and Security/System/Advanced system settings/Environment variables.  
3. In the Environment Variables window, under *System variables*, select the `Path` variable and click Edit.  
4. To the end of the value field, add a semicolon if need be and add the location of the Python installation. If this is C:\Python, add `C:\Python;C:\Python\Scripts`.

###### Installation Details: Windows 10

Python must be able to run from Command Prompt. The Python environment variable must be created, similar to how the JAVA_HOME variable was setup.  

1. Find the installation folder for Python 3.6, which is usually C:\Users\[username]\AppData\Local\Programs\Python\Python36-32, unless you specified a directory such as C:\Python during installation. 
2. Click the Search Windows icon. Enter into the search bar 'environment variable' and select *Edit the environment variables for your account*.  This will open the *Environment Variables* window.
3. In the Environment Variables window, under *User variables for [your username]*, select the `Path` variable and click Edit. 
4. Click *New*. Enter the location of Python (e.g., C:\Python), then a semi-colon, and then the location of Python Scripts (e.g., C:\Python\Scripts). Hit Enter.
5. That line should now look like C:\Python;C:\Python\Scripts. Click OK to exit the Path window. Click OK to exit the Environment Variables window.

### Opening Command Prompt
###### Windows 7
Start/All Programs/Accessories/Command Prompt  
To see a list of folders, type `dir` and press enter. This lists all the directories (folders) in the current directory. To navigate to one of those directories, enter `cd FolderName` and use quotes around the folder name if the name contains spaces, such as `cd "Folder Name"`. To navigate backwards, type `cd ..`. [More tutorials](http://ss64.com/nt/cd.html).

###### Windows 10
Click the Search Windows icon. Type cmd. Click on the Command Prompt in the search results.
To see a list of folders, type `dir` and press enter. This lists all the directories (folders) in the current directory. To navigate to one of those directories, enter `cd FolderName` and use quotes around the folder name if the name contains spaces, such as `cd "Folder Name"`. To navigate backwards, type `cd ..`. [Index of Command Prompt commands](https://ss64.com/nt/).


## Using bagbatch.py

##### Overview

1. Using [Command Prompt](https://github.com/js0430/BagBatch#opening-command-prompt), navigate to the directory containing bagbatch.py
2. Enter `python bagbatch.py <command>` or `python bagbatch.py <command> <dir>` where `<dir>` is the parent directory containing the subdirectories to be bagged.  
  Commands are as follows:  

 - baginplace: Creates a bag-in-place.  The source must be a directory on a filesystem and may already have a data directory.
 - update: Updates the manifests and (if it exists) the bag-info.txt for a bag.
 - verifyvalid: Verifies the validity of a bag.

##### Usage

_Input_: Parent directory with subdirectories to bag, verifyvalid, or update.  
_Output_: Parent directory with bagged subdirectories.  
_Dependency_: BAGIT\_INST_PATH.txt  
The first time bagbatch.py is run, it will create BAGIT\_INST_PATH.txt and prompt for the path of the BagIt installation. Within this folder, there will be a folder named 'bin' containing bag.bat. This path may be  "C:\Program Files\bagit-X.X.X". The path will be saved in BAGIT\_INST_PATH.txt. Each time bagbatch.py is run, it will validate this location.  

Possible Terminal/Command Prompt inputs:  

1. `python bagbatch.py <command> <directory>`  
2. `python bagbatch.py <command>`: Prompts for directory to run the command on  
3. `python <directory>`: Automatically uses the `baginplace` command
4. `python bagbatch.py`: Prints the usage instructions
5. `python bagbatch.py help` or `python bagbatch.py version`: Prints the usage instructions

##### Detailed Instructions

1. Open [Command Prompt](https://github.com/js0430/BagBatch#opening-command-prompt) and navigate to the directory containing bagbatch.py. For example, if it's in a folder on the desktop, enter "cd Desktop/folder".  
2. Enter `python bagbatch.py <command>` using an [accepted command](https://github.com/js0430/BagBatch#usage). Press 
  enter and the current status will be printed to the screen. The program will prompt for the folder containing the directories to run this command on. To prevent this popup, you can instead enter `python bagbatch.py <command> <dir>` where `<dir>` is the directory that contains all the subdirectories that need to be bagged. Type the path in or drag-and-drop the folder from the Finder/Explorer menu. Press enter. If no command is enter, baginplace will be used.  
3. If this is the first time bagbatch.py is run, you will be prompted for the BagIt installation directory. This folder name will look like `bagit-X.X.X` where the X.X.X is the version number. Within this folder, there must be another folder named 'bin' containing the file bag.bat.  
4. Depending on the size of the files, it may take a while to bag. The program is done once "Bags complete" is printed.


## Setting up a new version of BagIt or changing the installation path
##### Overview
The BagIt installation path used by bagbatch.py must be manually deleted or changed.

 - Option 1: Delete `BAGIT_INST_PATH.txt`, located in the same folder as bagbatch.py, and run bagbatch.py. It will prompt for the location of the new installation.
 - Option 2: Manually edit `BAGIT_INST_PATH.txt` to the location of the new installation


##### Detailed Instructions

`BAGIT_INST_PATH.txt` contains the path to BagIt's bag installation. This path 
will look similar to `"C:/Program Files/bagit-X.X.X/bin"`.

Each time bagbatch.py runs, it will validate this path, checking to see that the directory and bag.bat exists. If the directory does not exists or it does not contain bag.bat, it will prompt for the correct path.  

If a new version of BagIt is installed and the old version is not removed, `BAGIT_INST_PATH.txt` must be manually edited. Either delete the file and run bagbatch.py and let it prompt for the installation directory, entering the new installation this time, or enter in the path to the new installation.


## Troubleshooting
If you are getting errors in Command Prompt such as

    Error occurred during initialization of VM  
    Could not reserve enough space for object heap  
    Error: Could not create the Java Virtual Machine.  
    Error: A fatal exception has occurred. Program will exit.

First, try closing any open programs except Command Prompt. If that doesn't work, restart your computer and try running bagbatch.py again. If the problem persists, follow these directions ([Windows](https://wiki.carleton.edu/display/carl/Bagit#Bagit-DownloadandinstallBagit)) to increase the amount of memory Java can access for BagIt.

### Java
 - Is Java (version 6, 7, or 8) installed? BagIt recommends Java 6, and BagBatch has been tested with Java 7 and Java 8.
 - Is Java correctly setup for Command Prompt usage? Enter `java -version` in Command Prompt to check the version. 
 - Is the JAVA_HOME environment variable setup correctly? [Follow these setup instructions](https://github.com/js0430/BagBatch#setting-up-the-java_home-environment-variable).  
 - If that does not work, try uninstalling and reinstalling Java, following [Java's download instructions](https://www.java.com/en/).

### Python
 - Is Python3.6 installed?
 - Is Python correctly setup for Command Prompt usage? Enter `python` in Command Prompt to check the version. 
 - For Windows, check to see if the Python environment variable is [setup correctly](https://github.com/js0430/BagBatch#installation-details). 
 - If that does not work, try uninstalling and reinstalling Python 3.6, following [Python's download instructions](https://www.python.org/).

### BagIt
Download BagIt 4.9.0 from the [Library of Congress on GitHub](https://github.com/LibraryOfCongress/bagit-java/releases/tag/bagit-4.9.0).

 - Which version of BagIt? BagBatch has been tested with BagIt 4.9.0.
 - Check that the downloaded folder for BagIt contains the folder `bin`. In `bin`, there must be a file called `bag.bat`. 

### BagBatch
 - Check your version of BagBatch by entering `python bagbatch.py`.
