# BeanZee
## Z80 development board
Schematics and Gerber files for a simple development board for the Z80 CPU. 

![](images/BeanZee_photo_corner.jpg)

This started out as a simple [Z80 breadboard computer](https://github.com/PainfulDiodes/z80-breadboard-computer) and the schematic is basically the same; please refer to the breadboard project for further background. See also my [BeanZee blog post](https://painfuldiodes.wordpress.com/2024/12/29/beanzee-z80-development-board/).

The board has a 10MHz Z80 CPU, a clock module, 32k RAM, 32k EEPROM - which needs to be programmed externally, a simple reset circuit and an [FTDI UM245R](https://ftdichip.com/products/um245r/) USB module.

I am (slowly) developing [Marvin](https://github.com/PainfulDiodes/marvin), a simple monitor program, through which I expect to provide the means to load and execute a program on the BeanZee via the USB interface.

## Schematics
  
![](images/BeanZee_schematic_1.png)

![](images/BeanZee_schematic_5.png)

As a development board, there are a number of connectors for experimentation. Address and data bus connectors, /RD, /WR, /IORQ and /MREQ allow the CPU to address external memory and ports.

![](images/BeanZee_schematic_3.png)

On board address decoding is minimal, which makes addressing collisions with external devices inevitable.

To work around this, connections between the CPU and the glue logic for IO and memory are brought out as header pins. This means it is possible to operate in one of three modes (independently selectable for IO and memory):

* Enable the internal devices
* Disable the internal devices (and use external devices)
* Connect external logic for selectively enabling internal devices (in combination with external devices)

JP1 (for IO) and JP2 (for memory) provide normal operation where pin 1 is connected to pin 2, and therefore the /IORQ or /MREQ control is passed into the glue logic to enable the normal use of onboard IO or memory. 

If the jumper is moved to connect pin 2 to pin 3, the onboard devices for either IO or memory will be disabled, and external devices are free to respond to the CPU.

Removing a link altogether would allow an external connection to pin 2 - an external circuit can then provide additional logic to control activation of the internal IO or memory, for example to make the addressing more specific.

![](images/BeanZee_schematic_2.png)

The clock module has an input (pin 1) to enable / disable operation. Pin 1 is accessible as /CLKINH on a socket alongside CLK - see the earlier connectors diagram. 

If /CLKINH is left disconnected the on-board clock will operate normally. If /CLKINH is taken low the clock will stop, and pin 5 will go into a high impedance state. This means that an external clock generator could be connected to CLK.

![](images/BeanZee_schematic_4.png)

![](images/BeanZee_photo.jpg)
  
![](images/BeanZee_PCB.png)

![](images/BeanZee_PCB_2.png)
