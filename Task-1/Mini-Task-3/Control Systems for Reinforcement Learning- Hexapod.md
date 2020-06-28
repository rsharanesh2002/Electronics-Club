# Control Systems for Reinforcement Learning- Hexapod

## Project Idea

The complete idea of the project is to make a hexapod using Reinforcement Learning as the key tool. For the implementation of it, an important part of it is to track the exact orientation of the hexapod at any time. That’s the whole idea of this project, to make a control system using Reinforcement learning. 

## Constraints

The constraints in this project are:

1. Reliability of the Data, the data that we transfer to the computer to visualize the orientation of the robot must be more accurate and reliable because tracking of the object’s orientation at any point of time is an important process in the pipeline of the whole hexapod project. In order to recreate the exact orientation of the hexapod at any time we need to produce the body movement along with the orientation of each leg of it. 
 
2. Delay in the Information of data, we need the real-time simulation of the hexapod’s orientation in the computer and so the delay in the data transmission from the sensor to the microcontroller and then to the computer and followed by visualization of the object in the computer. 

3. Wiring Ideas, here in the hexapod there are 18 DOF and so there will be 18 servo motors and the extra sensors which we use to determine the hexapod’s position and orientation in real-time. So, due to a large number of components, the wires will be messed up and we need a proper wiring solution in order to have a smooth movement of the hexapod. 

## Proposed Idea

### Sensors:

The sensor here used must be able to keep a track of all possible movement of the hexapod and recreate the exact position and orientation of the hexapod at any instance of time. In our hexapod, we have 18 DOF (3 motors on each leg), so our job is to observe the movement of the base of the hexapod and also the movement of each of the legs of the hexapod.
 So, in order to establish it, we could use a 3-axis accelerometer along with gyro sensor (MPU-9250) to measure the movement of the base of the hexapod in all three axes. Also to track the movement of each leg of the hexapod we could use the flex sensor along each leg of the hexapod. By using the flex sensor on both the outer and inner sides of the leg. We can integrate both of them together and then produce the complete orientation of the hexapod at any instance of time. 
The idea is to transmit the sensor data from the MPU-9250 and the flex sensors on each leg of the hexapod to a microcontroller which in turn sends the data to the computer wirelessly.

### Microcontroller:

The microcontroller that we use here in order to transmit the sensor data should have a certain specification like it must be able to transmit data wirelessly, there must not be any delay in the transmission process and the data must be transmitted without any error in the transmission process. Based on the above-mentioned specs, we could use an ESP32 module as the micro-controller here in order to transmit them. The Bluetooth part in the ESP32 module works more similar to the way in which the serial communication would occur, and so this will be more suited to our application. The important feature of the microcontroller is that it must be compatible with both the sensors as well as the simulation environment that we use to visualize the data.

### Simulation Environment:

The simulation environment used here is the Blender software, which is a free and open-source 3D creation suite. It supports the entirety of the 3D pipeline—modeling, rigging, animation, simulation, rendering, motion tracking, video editing, and 2D animation pipeline.
With the help of a few python scripts, we could be able to produce the exact orientation and movement of the hexapod at any time. The sensor data from the MPU-9250 sensor and the flex sensor is transmitted through the microcontroller from the hexapod, using the PySerial library in python, we can establish communication from the microcontroller and the computer. Later on, using the python script, we can process the data received from the on-board sensors and produce the output on the screen by passing them to an exact replica of our hexapod created on the software.

### Wiring Idea:

Here the hexapod has 18 DOF, which means there are 18 servo motors connected, and also in order to track the exact position and orientation of the hexapod we employ sensors on each leg to acquire the data about the orientation and movement of each leg. So there will be 6 sensors in total, one in each leg. There will 3 servo motor on each leg and one sensor. We need to wire the motors and the sensors properly in order to have them in proper connection, if the wires are messed up, the wires would get pulled off if there were any jerks. So, in order to have a proper wiring solution, we could use JST connection wires. For each leg, we could have a separate tube through which these JST wires will be kept. In a single there are three motors and two sensors, the whole long tube will run completely from the start of the leg till the last motor, in between wherever the motors and sensors have placed a hole can be made and wire can be pulled out to connect them to the motor or sensor.

Instead of having a tight connection in the sense of keeping wire to the exact length required, we can have the wire a slightly longer, and then they can be rolled up and kept at the edge where the leg is connected to the base. The idea is similar to that of an extension box, wherein the wire can be pulled out if required and if it’s not required we could pull it back. The wire that is rolled up and kept can be placed in a roller with a motor shaft connected to the winder, if the wire is needed it can be released automatically and if less required then it can be rolled back. The whole idea is to make it like an automated wire extender and winder. The motor can be adjusted on whenever the wires are needed to be pulled out and when it needs to be pulled back into the winder.



## Pipeline:

The main processes involved in this project are:

Sensors(MPU-9250 and flex sensors) => Microcontroller => Serial Communication(using the Bluetooth part of the ESP32) => Receive data => Process the data => Simulate the object 

|Part of the Pipeline/Component Used|Idea of Implementation|Advantages|Disadvantages|
|:---:|:---:|:---:|:---:|
|Sensor-1: MPU-9250 | MPU-9250 is a three in one sensor with the functionalities of a 3-axes accelerometer, gyroscope, and magnetometer.|Using this on the base of the hexapod, we could be able to track the exact movement and orientation of the body of the hexapod along all the three axes. Easy to simulate on the blender simulation environment.| A bit costlier and (It isn’t that accurate but tolerable). There is an error called drift error in it which gets accumulated due to its constant measuring of changes and rounding off its calculated values.|
|Sensor-2: Flex sensor|Flex sensor, as the name suggests, the sensor is used to trace the exact flexibility of any object to which it is being attached to.|It’s pretty much easier to track the exact movement and orientation of each leg of the hexapod. Each leg of the hexapod has 3 motors each and there are 2 separate shafts that connect them, so if we were to use the MPU-9250 sensor then we need two for each leg which would increase the complexity and the cost. So, this is a really cool sensor that can be used in this application.| Cost, its a bit costlier when compared to other sensors. Due to its fragility, it’s difficult to solder them. After long usage, some errors might occur due to the change in the flexibility of the sensor itself.|
|Microcontroller ESP32|To use the microcontroller ESP32 to collect the data from the MPU-9250 sensor and the 6 flex sensors, and transmit them wirelessly to the computer. For the transmission purpose, we use the Bluetooth part that comes in-built with the ESP32 module.|The pretty cool advantage of using ESP32 is that it has a built-in Bluetooth module that can be used to transmit data wirelessly and also the Bluetooth communication using ESP32 is more similar to the Serial communication.|The communication system is constrained by the range. The transfer will have some sort of delay not real-time exactly.|
|Python Scripting (Receive and process data)|The data that is being transmitted from the microcontroller needs to received by the simulation environment. For that, we use a python script that will run on the simulation environment.|The python programming language has the built-in PySerial Library, that is needed for establishing serial communication. The remaining data processing can be done just by using python alone.|Needs good coding skills with knowledge of all commands.
|Simulation Environment (Blender)|Blender is used here to create the exact 3D replica of our hexapod and then using the data from the sensors the orientation of the hexapod is produced on it at any time.|Blender has built-in capabilities to run python scripts, create 3-D objects and simulate them for motion capturing, etc.,|Need some experience in fusion360 or unity to play with blender.|

## Resources Used:
### MPU-9250 IMU Sensor: ([Datasheet](https://invensense.tdk.com/wp-content/uploads/2015/02/PS-MPU-9250A-01-v1.1.pdf))
The MPU-9250 IMU sensor is a combination of a 3-axes accelerometer, a gyroscope, and a magnetometer. It can be connected easily to ESP32 since it is I2C compatible. So, we use this sensor and then deploy serial communication with ESP32 in order to transfer the sensor data. Also, another ease of using it is there are few built-in libraries from adafruit for this sensor.(Check it out [here](https://www.arduinolibraries.info/libraries/mpu9250))
![MPU-9250](https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcR2rgbWwEG4rbEoOeIdo8llTYxKOqsvuaSkBAksPdMjK7HbZFM0&usqp=CAUhttps://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcR2rgbWwEG4rbEoOeIdo8llTYxKOqsvuaSkBAksPdMjK7HbZFM0&usqp=CAU)

### Flex Sensor:
A flex sensor or bend sensor is a sensor that measures the amount of deflection or bending. Usually, the sensor is stuck to the surface, and resistance of sensor element is varied by bending the surface. Here we have six legs and so we use 2 flex sensors on each leg, one on the top and other on the bottom. So, the number of flex sensors used here is 12.

The coding part of flex sensor is too easy and can be jut done with the help of `sensorval=analogRead(pin_number)`.

Flex sensors can be used to make cool stuffs, check them [here.](https://www.youtube.com/watch?v=xDyV6u1SIP0)

The circuit diagram of how to use it with ESP32 can be found [here.](https://www.circuito.io/app?components=513,8606,360217)

Do find out how to get Analog Input using ESP32 and arduino IDE [here.](https://randomnerdtutorials.com/esp32-adc-analog-read-arduino-ide/) 
![Flex Sensor](https://cdn.sparkfun.com/assets/learn_tutorials/5/1/1/example_circuit_bb.png)

### Microcontroller ESP32:
The main reason of ESP32 being used here is because of it's bluetooth module, the bluetooth module of ESP32 module supports Serial Communication and so we could use it in a far easier way to transfer the sensor data to the computer.
The total number of flex sensors used are 12 and each flex sensors need an analog pin and the MPU-9250 sensor needs 2 anlog pins, so a total of 14 ADC pins are required here. Fortuantely ESP32 has around 15 ADC pins and so I think there won't problems with regards to the pins and a need for Mux'es won't occur here.
![Esp32_pinout](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2019/05/adc-pins-esp32-f.jpg?w=840&ssl=1)

## References:
1. https://www.youtube.com/watch?v=sGjVTMpYa7o - For the MPU-9250 based implementation of the orientation of the base of the hexapod on the simulation environment.
2. http://www.rignitc.com/motion-capture-glove/ - For the flex sensor, a similar use case as of ours.
3. https://www.youtube.com/watch?v=xDyV6u1SIP0 - For the flex sensor part.
