# Lightweight Arduino GSM Mobile Phone 
## Description
The lightweight mobile is capable of the following National/International features:
* Make Calls
* Receive Calls
* Send SMS
* Receive SMS
It uses GSM SIM900A module to connect to the mobile network. It is an adorable all-in-one cellular module that lets you add voice, SMS and data.
For the display purpose we use Nextion HMI TFT Display, Nextion adopts a new and easy way to interface any of your projects through UART. Its easy-to-use configuration software (Nextion Editor) enables us to design our own interfaces using GUI commands. Now coming to the coding part we use Nextion to write .hmi code for using the display and then arduino IDE to write code for communicating the GSM SIM900A and the Display via arduino which is the microcontroller here.
 
## What is a SIM900A GSM Module ?
The SIM900A is a readily available GSM/GPRS module,used in many mobile phones and PDA. The module can also be used for developing IOT (Internet of Things) and Embedded Applications. SIM900A is a dual-band GSM/GPRS engine that works on frequencies EGSM 900MHz and DCS 1800MHz. SIM900A features GPRS multi-slot class 10/ class 8 (optional) and supports the GPRS coding schemes CS-1, CS-2, CS-3 and CS-4.Along with it comes with the friendly RS232 which can be easily interfaced with any MCUs, the baud rate is adjustable from 9600 – 115200 through AT Commands.

The two types of cellular telephony radiation use different carrier frequencies and give different frequency spectra, but they usually also differ in intensity, as GSM 900 MHz antennas operate at about double the power output than the corresponding DCS 1800 MHz ones.

DCS 1800 also known as Personal Communications Network (PCN). An upbanded version of GSM, the pan-European digital cellular radio system. DCS 1800 operates in the 1800 MHz (1.8 GHz) range, rather than the 900 MHz range of GSM.
 
## What is Nextion NX8048T070 - Generic 7.0" HMI TFT LCD Touch Display?
Nextion is a seamless Human Machine Interface (HMI) solution that provides a control and visualization interface between a human and a process, machine, application or appliance. Nextion is mainly applied to Internet of thing (IoT) or consumer electronics field. It is the best solution to replace the traditional LCD and LED Nixie tube.Nextion includes a hardware part (a series of TFT boards) and a software part (the Nextion editor). The Nextion TFT board uses only one serial port to communicate. It lets users avoid the hassle of wiring. We noticed that most engineers spend much time in application development but get unsatisfactory results. As a solution to this situation, Nextion editor has mass components such as button, text, progress bar, slider, instrument panel etc. to enrich the interface design. Furthermore, the drag-and-drop function ensures that users spend less time in programming, which will reduce 99% of their development workloads. With the help of this WYSIWYG editor, designing a GUI is a piece of cake. It's easy to adapt Nextion family HMI to existing projects. Users just need to provide it with a UART. UART is Universal Asynchronous Reciever/Transmittter,  is a computer hardware device for asynchronous serial communication in which the data format and transmission speeds are configurable. The electric signaling levels and methods are handled by a driver circuit external to the UART. A UART is usually an individual (or part of an) integrated circuit (IC) used for serial communications over a computer or peripheral device serial port. One or more UART peripherals are commonly integrated in microcontroller chips. A related device, the universal synchronous and asynchronous receiver-transmitter (USART) also supports synchronous operation.
 
 
## Project Image
![](https://hackster.imgix.net/uploads/attachments/304648/img_9535_vbiwaba652_k5ugaKpEN9.JPG?auto=compress%2Cformat&w=680&h=510&fit=max)

