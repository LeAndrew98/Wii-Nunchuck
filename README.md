# Wii-Nunchuck
Wii Nunchuck (0x52)

![nunchuk](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/nunchuk.jpg)

# Table of Contents
1. [Introduction](#introduction)
2. [Budget for Materials Required](#budget-for-materials-required)
3. [Time Schedule](#time-schedule)
4. [Assembly of Pi](#assembly-of-pi)
5. [Wiring](#wiring)
6. [PCB Design Files](#pcb-design-files)
7. [PCB Soldering](#pcb-soldering)
8. [Power Up](#power-up)
9. [Case Design](#case-design)
10. [Assembly for Hardware](#assembly-for-hardware)
11. [Testing](#testing)
12. [Reproduction of Project](#reproduction-of-project)

### Introduction

The Wii nunchuk is a device used to play Wii games. It consists of a joystick and 2 buttons, the z button and the c button. When attached to a Raspberry Pi, and I2C is enabled, you should be able to read the X and Y axis direction of the joystick, the X, Y and Z axis of the actual controller, and if either of the buttons are being pressed. With my project I want to take those values and store them into a database. You can find the system diagram that I created [here](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/UML%20Diagram.pdf).


### Budget for Materials Required

 
### Time Schedule


### Assembly of Pi
If you follow these steps on how to set up the Raspberry Pi 3 B+ properly, you will have the ability to log in and make sure that your sensor is connected prperly.

1. Format an SD card with a minimum of 8GB to be used for the OS of the Pi. To download a SD card formatting software usw this link: https://www.sdcard.org/downloads/formatter_4/index.html

2. Download and unzip the latest version of the OS for the Raspberry Pi to your SD card. Download NOOBS in the link as that will ensure that you will have almost everything required when starting: https://www.raspberrypi.org/downloads/noobs/   

3. When NOOBS is on the SD card, remove it from the pc and insert it in the Pi. Before powering on your Raspberry Pi, make sure that your monitor, keyboard, mouse, HDMI, and any other device you want to connect is connected. Once everything is connected, you can plug in the power and the Raspberry Pi will automatucally turn on.

4. Upon the boot up session, select Raspbian as the operating system for the Pi and follow the instructions as they appear. You may also change the keyboard layout on the bottom during intial boot.

5. Once installation is completed, you should be brought to the desktop. Connect yourself to either Wifi or wired connection in order to perform the next few steps.

6. Open the terminal in the top left corner of the screen and input the following lines:
	
  
		wget https://raw.githubusercontent.com/six0four/StudentSenseHat/master/firmware/hshcribv01.sh \  
		-O /home/pi/hshcribv01.sh  
		chmod u+x /home/pi/hshcribv01.sh  
		/home/pi/hshcribv01.sh  


7. Now it is time to set up a VNC connection so that you can access your Pi on any computer screen. From the Start Menu, go -> Preferences->Raspberry Pi Configuration->Interfaces, then set VNC to Enabled. Now on the destop in the top right corner, you should see a VNC logo. When you click it you should see an IP address for your Pi which will be used to connect it via the VNC software. On the computer you would like to use, download VNC viewer here: https://www.realvnc.com/en/connect/download/vnc/

8. Once the software is installed, connect the ethernet cable from the Pi to the monitor that you want to use so you have a direct connection. Now you can simply input the same address you found in the Pi in the VNC software and it should connect.

9. To turn off the Pi, type sudo powerdown in the terminal or go to the menu and press shutdown. 



### Wiring


### PCB Design Files


### PCB Soldering


### Power Up



### Case Design 


The case is created by cutting pieces of acrylic using a lazer cutter from the Prototype lab in Humber College. 


### Assembly for Hardware


### Testing


### Reproduction of Project

If you follow all of these steps correctly, you should be able to recreate my project.
