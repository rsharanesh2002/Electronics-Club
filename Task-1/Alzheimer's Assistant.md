# Alzheimer's Assistant

## Description
This device ( a kind of smartwatch) will carry out the following tasks
1. Reminding the patient of carrying out tasks, he/she has to do daily (such as medications, exercise, etc)
2. Monitor where the patient is in the house
3. Alert the caretakers in case of an emergency of any sort
4. Display the time (it's a watch, after all!)
5. It should be portable, and easy to use, even for an elder patient

To perform the above task, there is a need for a variety of sensors, but in order to be constrained with the size, the best choice would be the Infineon sensor hub nano, whose size is small and also has BLE capabilities. With accurate pressure sensing, it could be used to detect if the patient has fallen and also tell where exactly the patient is in the house.

It has a DPS310 barometric pressure sensor, which sends its data through the evaluation board via Bluetooth. The pressure, altitude, and temperature values can be viewed in the Android app by Infineon as well as SES2G evaluation software.
For the Alzheimer's Assistant to work without an Android phone in between(should be a wearable which can work by itself), as well as have the ability to connect to a smartphone to view the sensor data. We use an Arduino MKR1000 board due to its small form factor and WiFi capability, and connect it by some method to the Sensor Hub Nano. Now to connect between the Sensor hub nano and the MKR1000 Wi-fi module a Bluetooth module is used. Finally, a display will be connected with the MKR1000 wi-fi module to view the data. In order to communicate from Arduino to sensor hub over Bluetooth, we use set AT commands in the Bluetooth module. Once we have got the data to our Arduino MKR1000 module, due to its wireless connectivity we can connect it to any IoT dashboard platforms to view the data.
 
## Infineon Sensor Hub:
	
The Sensor Hub Nano enables the user to evaluate Infineon’s DPS310 pressure sensor. Due to the small size of the evaluation kit and its Bluetooth connectivity, it is very easy to use the kit for prototyping and evaluation in real-life applications. The software GUI and Android Apps, that are provided along with the kit, help in capturing pressure sensor data during evaluation. The Sensor Hub Nano kit contains XMC4500 MCU which communicates with DPS310 pressure sensor and sends data to the user via a Bluetooth module. The kit is powered by a battery, which can be recharged via the Micro-USB port. DPS310 is a barometric pressure sensor with high accuracy and low power consumption. The pressure sensor MEMS element is based on capacitive sensing principle and hence guarantees high precision over temperature. The small package (2mm x 2.5mm x 1mm) makes DPS310 ideal for use in mobile and wearable devices. 
 
## HC-05 Bluetooth module
The HC-05 is a very cool module that can add two-way (full-duplex) wireless functionality to your projects. You can use this module to communicate between two microcontrollers like Arduino or communicate with any device with Bluetooth functionality like a Phone or Laptop. There are many android applications that are already available which makes this process a lot easier. The module communicates with the help of USART at 9600 baud rate hence it is easy to interface with any microcontroller that supports USART. We can also configure the default values of the module by using the command mode. This is a Wireless module that could transfer data from your computer or mobile phone to microcontroller or vice versa then this module might be the right choice for you.  

The HC-05 has two operating modes, one is the Data mode in which it can send and receive data from other Bluetooth devices and the other is the AT Command mode where the default device settings can be changed. We can operate the device in either of these two modes by using the key pin as explained in the pin description.

It is very easy to pair the HC-05 module with microcontrollers because it operates using the Serial Port Protocol (SPP). Simply power the module with +5V and connect the Rx pin of the module to the Tx of MCU and Tx pin of module to Rx of MCU as shown in the figure below

## Project Image
 ![](https://hackster.imgix.net/uploads/attachments/356808/display_sensor_values_Ls7Go0jx6o.jpg?auto=compress%2Cformat&w=680&h=510&fit=max)
 
