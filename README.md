# Atmega Custom Bootloader
Easy custom bootloader circuit for Atmega chips.

There were many ways to burn the bootloader, but I found them quite messy if I had to burn the bootloader for several blank chips. Thanks to [WestfW](https://github.com/WestfW) for writing the loader that makes the job easy and less messy!. With that, built a custom circuit for the same purpose.


## Required Stuff

* Arduino UNO - (Acts as device programmer)
* 2 Capacitors - 22pF
* 1 Oscillator - 16MHz
* Female Headers - 2 x 14Pin, 1 X 6Pin
* PCB board

## Steps

1. Design a PCB in the following way show below :

![PCB](https://github.com/alshell7/AtmegaCustomBootloader/blob/master/CustomBootloader_pcb.png "PCB")

2. Solder the components :
> This is just a rough design if you are working on a prototype PCB board

![Connections](https://github.com/alshell7/AtmegaCustomBootloader/blob/master/Connections.PNG "Connections")

3. Place the Atmega chip on the PCB board (over the female header pins) and make the connections :
    * VCC - Arduino: PIN 9
    * GND - Arduino: GND
    * 13 - Arduino: PIN 13
    * 12 - Arduino: PIN 12
    * 11 - Arduino: PIN 11
    * RESET - Arduino: PIN 10

4. [Download OptiLoader](https://github.com/WestfW/OptiLoader/archive/master.zip) and open it in your Arduino IDE

5. Connect Arduino to your PC

6. Upload the the sketch

7. To see the progress of the process 
    * Open **Serial Monitor**
    * Set the baud rate to **19200**
    * You should see if it were successful burning the bootloader or not
```
OptiLoader Bootstrap programmer.
2011 by Bill Westfield (WestfW)

Target power on! ...
Starting Program Mode [OK]

Reading signature:950F
Searching for image...
  Found "optiboot_atmega328.hex" for atmega328P
  Start address at 7E00
  Total bytes read: 502

Setting fuses for programming
  Lock: 3F FFE000  Low: FF FFA000  High: DE FFA800  Ext: 5 FFA400

Programming bootloader: 512 bytes at 0x3F00
  Commit Page: 3F00:3F00
  Commit Page: 3F40:3F40
  Commit Page: 3F80:3F80
  Commit Page: 3FC0:3FC0

Restoring normal fuses
  Lock: 2F FFE000

Target power OFF!

Type 'G' or hit RESET for next chip
```


## My version :wink:
![Custom](https://github.com/alshell7/AtmegaCustomBootloader/blob/master/CustomMade.jpeg "Custom")
