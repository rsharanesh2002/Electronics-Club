# Breadboard Computer Programmer
## Description
The idea of the project is to use Arduino as a substitute EEPROM and make a breadboard computer. The role of arduino is to read data from memory and write data to memory. The easiest and least intrusive (to the breadboard computer) way to do that is to use the same interface that the memory module already has: the bus and control signals. The Arduino digital I/O pins are bi-directional, so connecting 8 of them directly to the bus allows the Arduino to read from and write to the bus. To make the RAM module read from or write to the bus all that is necessary is to set the MI/RI/RO signals accordingly.
Now those signals are usually driven by the control logic's EEPROMs so having the Arduino control them too would lead to conflicts and possible short-circuit situations. However, the AT28C16 EEPROMS has a Chip Enable (CE) input that puts all data outputs into a high-z state - which then allows the Arduino to manipulate the signals.
## EEPROM
EEPROM (also E2PROM) stands for electrically erasable programmable read-only memory and is a type of non-volatile memory used in computers, integrated into microcontrollers for smart cards and remote keyless systems, and other electronic devices to store relatively small amounts of data but allowing individual bytes to be erased and reprogrammed.
EEPROMs are organized as arrays of floating-gate transistors. EEPROMs can be programmed and erased in-circuit, by applying special programming signals. Originally, EEPROMs were limited to single byte operations, which made them slower, but modern EEPROMs allow multi-byte page operations. An EEPROM has a limited life for erasing and reprogramming, now reaching a million operations in modern EEPROMs. In an EEPROM that is frequently reprogrammed, the life of the EEPROM is an important design consideration.
## Chip Enable
CE (Chip Enable) is a memory select signal and the memory is selected when it is set at low level. This is used to assign a specific address by adding an address-decoded signal.

## Functions that can be performed by this breadboard computer are
1. Save a program from breadboard computer RAM
2. Load a program into the breadboard computer RAM
3. Auto-run a saved program when the breadboard computer starts up
4. Inspect and modify memory contents via a serial connection
5. Program the breadboard computer in assembly language
6. Disassemble memory contents
7. Single-step instruction by instruction
8. Set breakpoints and run up to breakpoint
 ## To read out the RAM/write out the RAM, the Arduino needs to do the following
1. set the EEPROM's CE signal high (i.e. disable the control logic)
2. output the first address to be read onto the bus
3. set the MI signal high and wait for a clock low-high transition
4. set MI low and RO high(to read out the RAM)/RI high(to write out from the RAM) and wait for a clock low-high transition
5. read the data byte from the bus
6. repeat from step 2 for all 16 addresses
7. set the EEPROM's CE signal low (i.e. re-enable the control logic)
## Project Image
 ![](https://hackster.imgix.net/uploads/attachments/323104/img_0238_x5yLqWOos2.JPG?auto=compress%2Cformat&w=680&h=510&fit=max)

