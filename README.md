# Codeblocks template for Arduino developement
> &copy; 2014-2014 Teodor Petrov
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

Code::Blocks SVN rev 9842, because there are some changes in the Scripted wizard plugin.

## Install

Certain files should be placed or symlinked inside the User data folder of Code::Blocks.
On Linux this is /home/$USER/.codeblocks/

1. You should create a symlink to the data folder of your Arduino install (/usr/share/arduino on Linux) to ~/.codeblocks/arduino
2. You should create a symlink for the wizard. Link the root of this repo to ~/.codeblocks/share/codeblocks/templates/wizard/
3. You need to install AVR compiler (AVR GCC) and set it up inside Code::Blocks

## Notes

Tested only on Linux. If you test it on Windows or OSX and make changes please provide patches.
