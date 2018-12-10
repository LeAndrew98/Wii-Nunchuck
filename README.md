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

To complete this project you would need to purchase these materials from my budget. One change that needs to be made to this budget, the IDC cables do not need to be purchased, and instead the purchase of the Akuru 3-in-1 kit Jumper Wires from amazon. You can find my budget [here](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/CENG317%20Budget.pdf).
 
 
### Time Schedule

This project took me about 4 months(a whole semester), but if parts are already acquired, I think that this project should only take around 4-5 days if they spend around 2-3 hours working on it. You can find my project schedule [here](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/CENG317%20Schedule.pdf). This schedule shows the timeline and milestones that I had to follow to be able to complete my project on time.

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

Before you begin to wiring, you should check the UEXT manual provided [here](https://www.olimex.com/Products/Modules/UEXT/resources/UEXT_rev_B.pdf)(on page 3) and you should also have the Raspberry Pi pins layout which you can find in your raspberry pi kit. These manuals will provide you information on the 10 pins you would need to connect in order to make your Wii Nunchuk work with your Raspberry Pi.

When the wiring is completed, this is what it should look like:

![wiring](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/Wiring.jpg)

### PCB Design Files


### PCB Soldering

Before soldering, make sure you have safetly glasses equipped along with having proper ventilation that contains a extractor arm for the fumes. A soldering toolkit is also required which is available in most labs. If you want help soldering, this video will help you learn
https://www.youtube.com/watch?v=3230nCz3XQA, if you are still unconfident there are people in the prototype lab will be willing to help you learn.

When soldering, you want to solder in the 20 pin header, making sure that it is on the bottom of the PCB as it needs to plug into the Raspberry Pi. When that is completed, you want to solder the 10 pin male header onto the other side of the PCB(top side). When this is completed, you need to put a piece of wire through each via and solder it on both the bottom and top side. This should be done for all 10 vias created.

When completed the top view should look like this:

![topview](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/PCBTop.jpg)

And the bottom view should look like this:

![bottomview](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/PCBBottom.jpg)


### Power Up

Once soldering is finished, you can connect your PCB to the Raspberry Pi and you can connect the Wii Nunchuk to the male header. Once connected boot up the Raspberry Pi and follow these steps:

1. Use sudo raspi-config to begin enabling I2C.

2. Select Interface Options, go to IC2 and select "Enable". Then click Finish.

3. Use sudo i2cdetect -y 1 to be able to see if your Wii Nunchuk is being seen by the Pi.

If this is done correctly you should see this output screen:

![deviceoutput](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/Device.JPG)

### Case Design 

When designing the case, I took the original case design from the dropbox provided, and extended the width of the base by 3/8 an inch and also extended the length by 0.2 inches, all in Corel Draw. You can find my Pi case diagram [here](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/PiCaseDiagram.pdf).

The case is created by cutting pieces of acrylic using a lazer cutter from the Prototype lab in Humber College. 


### Assembly for Hardware

Once the case is created, you can begin to assemble your hardware. When assembling the case it is best to put the Raspberry Pi onto the base with the PCB on, making sure that the holes of the Raspberry Pi line up with the holes made in the base of the case, you can put the 4 screws through and this would secure the Pi down onto the base. Once that is complete, you can snap on the other sides of the case and the top of the case.

When everything is put together it should look like this:

![case](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/case.png)

### Testing

To test the sensor I used code provided from Olimex's github that provides me with python code that will test the Wii Nunchuk's values and would provide the output screen. You can find Olimex's Github [here](https://github.com/OLIMEX/raspberrypi/blob/master/MOD-Wii-NUNCHUK/mod-nunchuck.py). Here is the code:

	#!/usr/bin/env python

	import smbus
	import sys
	import os
	import time

	def Initialize():
    "Initalize MOD-Wii-UEXT-Nunchuck"
    
    bus = smbus.SMBus(0)
    address = 0x52
    command = 0xF0  
    data = 0x55
    
    bus.write_byte_data(address, command, data)
    return


	def main():
    print "MOD-Wii-UEXT-Nunchuck"
    bus = smbus.SMBus(0)
    address = 0x52
    command = 0x00
    Initialize()
    while True:
        time.sleep(0.1)
        os.system('clear')
        buf = bus.read_i2c_block_data(address, command, 6)
        
        data = [0x00]*6
        
        for i in range(len(buf)):
       #     buf[i] ^= 0x17
        #    buf[i] += 0x17
            data[i] = buf[i]
        
        z = data[5] & 0x01
        c = (data[5] >> 1) & 0x01
        
        data[2] <<= 2
        data[2] |= (data[5] >> 2) & 0x03
        
        data[3] <<= 2
        data[3] |= (data[5] >> 6) & 0x03
        
        print "Analog X: %d" %(data[0])
        print "Analog Y: %d" %(data[1])    
        print "X-axis: %d" %(data[2])
        print "Y-axis: %d" %(data[3])
        print "Z-axis: %d " %(data[4])
        
        if z == 1:
            print "Button Z: NOT PRESSED"
        else:
            print "Button Z: PRESSED"
            
        if c == 1:
            print "Button C: NOT PRESSED"
        else:
            print "Button C: PRESSED"
    

	if __name__ == '__main__':
    main()

The output screen should look like this:

![output](https://github.com/LeAndrew98/Wii-Nunchuk/blob/master/Documentation/Output.png)


### Reproduction of Project

If you follow all of these steps correctly, you should be able to recreate my project.
