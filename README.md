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

## Requires

Arduino 1.6.9. Using 1.0.x won't work. I've not tested anything older than 1.6.9.
Code::Blocks SVN rev 9843, because there are some changes in the Scripted wizard plugin.

## Install

Certain files should be placed or symlinked inside the User data folder of Code::Blocks.
On Linux this is /home/$USER/.local/share/codeblocks

1. You need to install AVR compiler (AVR GCC) and set it up inside Code::Blocks
2. You should create a symlink for the wizard. Link the root of this repo to ~/.local/share/codeblocks/templates/wizard/arduino

3a. Create the local config.script if it does NOT already exist
   ```
   mkdir -p ~/.local/share/codeblocks/templates/wizard
   cp /usr/share/codeblocks/templates/wizard/config.script ~/.local/share/codeblocks/templates/wizard/config.script
   ```
3b. Add the following two lines in the RegisterWizards function insde the file ~/.local/share/codeblocks/templates/wizard/config.script

   ```
   RegisterWizard(wizProject, _T("arduino"), _T("Arduino Project"), _T("Embedded Systems"));
   RegisterWizard(wizTarget,  _T("arduino"), _T("Arduino"),         _T("Embedded Systems"));
   ```
4. After you create a project with the wizard the Global Variables dialog will show up and will
ask you for the path to the root of the Arduino project.

## Notes

Tested only on Linux. If you test it on Windows or OSX and make changes please provide patches.
