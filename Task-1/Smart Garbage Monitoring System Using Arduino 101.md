# Smart Garbage Monitoring System Using Arduino 101
## Description 
One of the main concerns with our environment has been solid waste management which impacts the health and environment of our society. The detection, monitoring, and management of wastes are one of the primary problems of the present era. The traditional way of manually monitoring the wastes in waste bins is a cumbersome process and utilizes more human effort, time, and cost which can easily be avoided with our present technologies. This is an IoT Garbage Monitoring system, an innovative way that will help to keep the cities clean and healthy.
This system gives a real-time indicator of the garbage level in a trashcan at any given time. Using that data we can then optimize waste collection routes and ultimately reduce fuel consumption. It allows trash collectors to plan their daily/weekly pick up schedule.
An ultrasonic sensor (A.K.A a distance sensor) will be placed on the interior side of the lid, the one facing the solid waste. As trash increases, the distance between the ultrasonic and the trash decreases. This live data will be sent to the microcontroller, the Arduino 101 then processes the data and through the help of WiFi(the Wi-fi module used here is Arduino MKR100) sends it to an app. There is an app that visually represents the amount of trash in the bin with a small animation. To connect to the internet we use a prebuilt platform called Blynk, which can be downloaded from the android play store for free.
## Arduino 101 vs Uno 
The Arduino Uno is a very simple board. It uses an ATMega328 processor — a basic, 8-bit microcontroller. Other than a USB interface, the Uno doesn’t provide anything else. For a basic project or one where you’ve already got external hardware, it gets the job done at a low cost.
The Arduino 101 uses the Intel Curie processor and adds an accelerometer/gyro chip and Bluetooth LE capabilities. That suggests to me that it’s aimed at robot makers
## Arduino MKR1000 
Arduino MKR1000 is a powerful board that combines the functionality of the Zero and the Wi-Fi Shield. It is the ideal solution for makers wanting to design IoT projects with minimal previous experience in networking.
## Why Base shield for Arduino?
Arduino Uno is the most popular Arduino board so far, however, it is sometimes frustrating when your project requires a lot of sensors or LEDs and your jumper wires are in a mess. The purpose of creating the Base Shield is to help you get rid of breadboard and jumper wires. With the rich grove connectors on the baseboard, you can add all the grove modules to the Arduino Uno conveniently! The pinout of Base Shield V2 is the same as Arduino Uno R3.
## Blynk app:
Blynk is a Platform with IOS and Android apps to control Arduino, Raspberry Pi, and the likes over the Internet. It’s a digital dashboard where you can build a graphic interface for your project by simply dragging and dropping widgets.

## Project Image
![Bin Image](https://hackster.imgix.net/uploads/attachments/331524/FR4GQO7J48PVZBX.MEDIUM.jpg?auto=compress%2Cformat&w=680&h=510&fit=max)
![App Image](https://hackster.imgix.net/uploads/attachments/331577/screenshot_(7)_SzfRuuhZz1.png?auto=compress%2Cformat&w=680&h=510&fit=max)


