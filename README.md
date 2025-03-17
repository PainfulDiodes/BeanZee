# BeanZee Z80 homebrew development board
A small Z80 based single-board-computer designed for experimentation.

Z80 CPU, 10 MHz clock, a simple reset circuit, 32K ROM, 32K RAM, FTDI UM245R USB module and the necessary glue logic.

Connectors provided for interfacing with the Z80: address, data, read, write, IO request, memory request, clock and reset.

The internal clock may be overridden by an external clock, and the internal memory and USB module may also be disabled via jumpers so that external devices can be used, or additional memory and IO selection logic added.

There is an accompanying [Marvin](https://github.com/PainfulDiodes/marvin) simple monitor program which can be used to inspect and modify memory contents and load and execute a program from the host computer. Example programs can be found in [BeanZeeBytes](https://github.com/PainfulDiodes/BeanZeeBytes).

See also:  
[Detailed README](README-DETAILED.md)   
[Marvin the monitor](https://github.com/PainfulDiodes/marvin)   
[Blog post](https://painfuldiodes.wordpress.com/2024/12/29/beanzee-z80-development-board/)  
[Hackaday project](https://hackaday.io/project/202193-beanzee)  
[MINT minimalist interpreter for BeanZee](https://github.com/PainfulDiodes/MINT)  
[Z80 breadboard computer](https://github.com/PainfulDiodes/z80-breadboard-computer) - the schematic is largely the same as BeanZee  

![](images/BeanZee_photo_corner.jpg)
  
![](images/BeanZee_schematic_1.png)

![](images/BeanZee_schematic_2.png)

![](images/BeanZee_schematic_3.png)

![](images/BeanZee_schematic_4.png)

![](images/BeanZee_schematic_5.png)

![](images/BeanZee_photo.jpg)
  
![](images/BeanZee_PCB.png)

![](images/BeanZee_PCB_2.png)
