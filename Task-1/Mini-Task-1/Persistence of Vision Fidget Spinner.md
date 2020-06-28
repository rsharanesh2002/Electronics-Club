# Persistence of Vision Fidget Spinner

## Description

This is a fidget spinner that uses the Persistence of Vision effect which is an optical illusion whereby multiple discrete images blend into a single image in the human mind. The text or graphics can be changed via Bluetooth Low Energy link by using a PC application that has been programmed in LabVIEW or by using a freely available smartphone BLE app.
One of the most important characteristics of this POV fidget spinner is that the displayed graphics doesn’t depend on rotation velocity, it keeps the track of rotation angle. Meaning that the displayed graphic is perceived the same at both, higher and lower rotational speeds (for instance, when the fidget spinner is slowing down when held in the hand).

It uses an enhanced Microchip PIC 16F1619 microcontroller as its core, which has a built-in Angular Timer peripheral which uses an omnipolar Hall sensor DRV5033 and one magnet to keep the track of current rotational angle and to display it uses strips of LEDs. 

## Working

It uses an enhanced Microchip PIC 16F1619 microcontroller as its core. The MCU has a built-in Angular Timer peripheral which uses an omnipolar Hall sensor DRV5033 and one magnet to keep the track of current rotational angle. The graphics are displayed using a total of 32 LEDs, 16 green and 16 red light-emitting diodes (nominal current 2mA). The diodes are driven by two 16 channel constant current shift register drivers TLC59282 connected in a daisy chain. 

In order to have remote access to the device, there are a Bluetooth Low Energy module RN4871 that communicates to the microcontroller via the UART interface. The device can be accessed from either a personal computer or a smartphone. The device is turned on by using a capacitive touch button which is embedded under the solder mask on the printed circuit board. The output from the capacitive IC PCF8883 is fed to the OR logic gate BU4S71G2. The other input to the OR gates is a signal from the MCU. The output from OR gates is connected to the Enable pin of a step-down converter TPS62745. By using this setup I am able to power on/off the device by using only one-touch button. Capacitive buttons can also be used to change between different modes of operation or for instance to turn on the Bluetooth radio only when needed in order to save energy.

The rotational angle is tracked "by hardware“ rather by software meaning that the CPU has a lot more time at its disposal to do other tasks. For that, it uses an Angular Timer peripheral which is built into the used microcontroller PIC 16F1619.

Input to the Angular Timer is a signal from Hall sensor DRV5033. The Hall sensor will generate a pulse every time a magnet passes by it. The Hall sensor is located at the spinning part of the device while the magnet is located on a static part for which the user holds the device. We use only one magnet that means that the Hall sensor will produce a pulse that is repeating every 360°.

At the same time, Angular Timer will generate 180 pulses per revolution in which every pulse represents 2° of rotation. It turns out that 180 pulses,  2° of rotation was the perfect distance between the two columns of a printed character. The Angular Timer handles all that calculation automatically and will adjust automatically if the time between the two sensor pulses changes due to the rotation velocity changing. The position of the magnet and Hall sensor is shown in the attached photo.

We have chosen BLE because it uses a very small amount of energy and the used chip RN4871 is only 9x11.5 mm in dimension, and also it changes the text dynamically and not just by hard coding it.

Via BT link it is possible to change the displaying text and its color - red or green. Battery level can also be monitored to know when it is time to replace the batteries. The device can be controlled via computer application programmed in LabVIEW graphics programming environment or by using a freely available smartphone BLE applications which has the ability to directly write to the selected BLE Characteristics of a connected device. For sending the information from a PC/smartphone to the device I used one Service with three Characteristics, each identified by a Handle.

In the top-left corner we have controls for starting up the National Instruments BLE server application. That is a command line application from NI which creates a bridge between BLE module on a computer and LabVIEW. It uses HTTP protocol to communicate. The reason for using this application is that LabVIEW only has native support for Bluetooth Classic and not for BLE.

Upon successful connecting, the MAC address of a connected device is displayed on the right and that part is not grayed out anymore. There we can set the moving graphics and its color or just send some pattern to turn the LEDs on or off when the device is not spinning, I have used that for testing purposes.

English alphabet font was generated using a freely available software "The Dot Factory“ but I needed to make a few modification before uploading it to the microcontroller.

The reason for that is PCB layout which is "not in order“, meaning the output 0 from LED driver is maybe not connected to the LED 0 on the PCB, OUT 1 is not connected to LED 1 but rather to LED15 for instance, and etc.. The other reason is the software is only allowed to generate a 2x8bit font but the device has 16 LEDs for each color so I needed a 16bit high font. So we need to make a software that would shift a few bits to compensate for PCB layout and combine them to one 16bit value. Because of that we need to develop a separate application in LabVIEW that takes the font generated in "The Dot Factory“ as input and transforms it to suit the needs of this project. Since the red and green LED PCB layouts are different we need to use two fonts. The output for the green font is shown in the picture below.
To summarise, It’s best to use the Angul Timer peripheral, because we were able to make a POV device which doesn’t depend on rotational velocity, so the quality of displayed graphics is kept the same at both higher and lower speeds.

By careful design we managed to implement a low energy solution which will prolong the battery life. As for the cons of this project, there is no way to charge the used batteries, so battery replacement every now and then is required. No-name batteries from the local store lasted about 1 months with every-day use.

Uses: 
This device can be used in various promotional purposes or as a teaching aid in electro-technics or physics classes for instance. It can also be used as a therapeutic aid to increase attention for those with Attention Deficit Hyperactivity Disorder (ADHD) or calm symptoms of anxiety.

Project Image:

![](https://content.instructables.com/FEB/8AF0/K8CD99MK/FEB8AF0K8CD99MK.LARGE.jpg?auto=webp&frame=1&width=370&fit=bounds)
![](https://content.instructables.com/FNG/HIRQ/K8CD99MM/FNGHIRQK8CD99MM.LARGE.jpg?auto=webp&frame=1&fit=bounds)

