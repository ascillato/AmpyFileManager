Ampy File Manager
-----------------
Windows GUI for the Adafruit MicroPython Utility


A simple GUI wrapper that executes the AMPY command to manipulate the files on an ESP8266 board running 
MicroPython.

It was written in C# in Visual Studio 2019, so you will need VS Express or better to compile it. It uses
the Scintilla editor control (https://github.com/jacobslusser/ScintillaNET), which allows for Python3 
syntax highlighting.

As a development tool, I wrote the utility to mainly just edit the files directly off of the device. I 
have also embedded a simple terminal emulator to send commands to the serial REPL.

A precompiled binary is available for download here:

	http://wezensky.no-ip.org/shared/AmpyFileManager.zip

PREREQUISITES:
	1. .Net Framework 4.5.2 or greater
	1. Python 
	2. Adafruit AMPY tool
	
HOW TO START:

- Unzip the archive to a convenient location
- Plug your MicroPython device into your computer and determine what com port it was assigned to
- Start the application by opening AmpyFileManager.exe
- Select the com port for your device (if there is more than one)
  The main window should appear with the files on the root of the device listed
  If there was a problem and the files were not listed, click on the Refresh button

HOW TO USE:

All the features are pretty self-explanatory, but here is just a short description of it's general use.

- To open a file for viewing or editing, select the file and click "Open" (or just double-click the filename)
- To go into a sub-folder select the folder and click "Open" (or just double-click the folder name)
- "New" will prepare a new file for editing
- "Load" will allow you to import a file
- "Delete" will delete the file from the device
- "Move" will allow you to move (or rename) a file
- "MKDIR" will allow you to create a sub-folder
- "Refresh" will reread the file list of the current directory
- "REPL" will open a serial terminal application

ADDITIONAL INFO:

- The backups (by default) are stored in a sub-folder of the directory where the EXE is located.
- Configuration setting are located in the AmpyFilemanager.exe.config file

CONFIG SETTINGS NOTES:

- 


CAVEATS:

- Because of some limitations, in order to use this tool you must follow this guideline...
  Directories will be recognized by their lack of an extension
  Editable files are recognized by their use of an extension
- The terminal is limited in it's capabilities
- Although it should work with any device that AMPY works with, it has only been tested with a Wemos D1 Mini 
  and a Witty Cloud Board
- This is mainly for text files (binary files will upload to the device but will not download correctly)
- Switching between the console and the editor (and back) is a little rough.
  You may have to "Refresh" or try again to get a feature to work.
  Sometimes the software will pause until the device is momentarily unplugged
  This is highly dependent on the type of application that is running