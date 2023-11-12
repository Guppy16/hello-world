# Guide to setup drone controller wirelessly using vJoy 

![radio-receiver-ftdi](https://github.com/Guppy16/hello-world/assets/48368985/86d53330-3ca5-4572-9b68-9bdd9dcd7719)

This is a guide to wirelessly connect your drone controller to your computer using vJoy. 

# Assumptions
- You don't have ELRS - if you do, your controller will likely have a bluetooth mode to connect the controller to your computer
- You must have a working drone receiver and FTDI chip connected like so:

<img src="https://github.com/Guppy16/hello-world/assets/48368985/f993de95-2a53-4a71-a10e-4a3e49a6802b" height="200">



1. Download the vJoy driver from [GitHub](https://github.com/jshafer817/vJoy/releases) or [sourceforge](https://sourceforge.net/projects/vjoystick/) and run the setup to install the driver. This driver allows the computer to recognise an input method as a joystick.
2. Download and install the vJoy Serial Feeder from [GitHub](https://github.com/Cleric-K/vJoySerialFeeder/releases). This provides a program to read data from a serial port and output to a virtual joystick (vJoy).
3. Open the vJoy Serial Feeder application and setup the channels as mentioned in the [readme](https://github.com/Cleric-K/vJoySerialFeeder)

The channel maps may look like so:

![image](https://github.com/Guppy16/hello-world/assets/48368985/2d34d9a7-96a3-44a6-9e93-c7ea7e2ed2c4)
