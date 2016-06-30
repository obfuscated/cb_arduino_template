# Codeblocks template for Arduino developement
> &copy; 2014-2016 Teodor Petrov
> under GNU General Public License

> &copy; 2012-2013 Scott Daniels (<http://provideyourown.com>)
> under GNU General Public License

> Portions are: &copy; 2012 Stanley Huang (<stanleyhuangyc@gmail.com>)
> under GNU General Public License

This project provides a project template for the Code::Blocks IDE, which allows easy creation of Arduino projects.
It is based on several other such templates. The template provided by Code::Blocks Arduino project is used as a base.
Its main goal is to provide easy to use standalone template, which can be used in vanilla Code::Blocks install.

##Features

* Dedicated project wizard for Arduino development
* Integrated Arduino core files and libraries
* Calls AVRDUDE for uploading (Flash and EEPROM) via USB or programmer as a post build step
* Allows the user to select what targets/devices he/she wants to build for
* Allows the user to choose the enabled libraries
* Setups every target to build object and binary files in a separate folders

## Requirements

The wizard requires minimum Arduino 1.6.9 to work properly. The Wizard does not support Arduino 1.0.x.
Code::Blocks SVN rev 9843, because there are some changes in the Scripted wizard plugin.

## Installation

1. Install and configure GCC AVR compiler in the Code::Blocks
2. Checkout or download the Wizard to your computer

On Windows:


On Linux:

1. Create the directory structure 
   `~/.local/share/codeblocks/templates/wizard/`
2. Create a link to the location of the wizard from the steps above:
   `~/.local/share/codeblocks/templates/wizard/arduino-> /<somelocation>/cb_arduino_template`
3. Copy the main config.script file to the local config locations:
   `cp /usr/share/codeblocks/templates/wizard/config.script ~/.local/share/codeblocks/templates/wizard/`
4. Add the following two lines in the RegisterWizards function to the file
   `~/.local/share/codeblocks/templates/wizard/config.script` if missing

   ```
   RegisterWizard(wizProject, _T("arduino"), _T("Arduino Project"), _T("Embedded Systems"));
   RegisterWizard(wizTarget,  _T("arduino"), _T("Arduino"),         _T("Embedded Systems"));
   ```
5. After you create a project with the wizard the Global Variables dialog will show up and will
ask you for the path to the root of the Arduino installation:
```
ls ~/bin/arduino-1.6.9/
arduino  arduino-builder  dist  examples  hardware  install.sh  java  lib  libraries  reference  revisions.txt  tools  tools-builder  uninstall.sh
```

## Notes

Tested only on Linux. If you test it on Windows or OSX and make changes please provide patches.
