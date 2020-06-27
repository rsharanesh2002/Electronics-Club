# Automated Navigation Robot With Gas (MQ-2), Temperature & Humidity (DHT11) Sensors 
## Description
This is a robot capable of navigating around obstacles in a room using the ultrasonic module HC-SR04 mounted on a Servo, this allowed the robot to look around to determine the best route to follow once an obstacle had been encountered. This isn’t anything hard, so there are some additional sensors in combination with a Bluetooth module, this allows the robot to gather environmental condition data then relay it back to an Android Application, from the Android Application you can also change the state of the robot from Navigation mode to idle where the robot will remain stationary but will still transmit sensor data.

The first step in this is the bot building driving the motors, to do that we use the standard L293D motor driver, the servo motor that holds the ultrasonic sensor. Further, then all the components namely Bluetooth module, temperature sensor, gas sensor, and the ultrasonic sensor are connected.
Next, the LCD display is connected to Arduino via an I2C module to display the robot’s current state information.
Now, it’s time for the coding part. 

**The algorithmic flowchart is**

![](https://cdn.instructables.com/FWP/XKGT/IPJZNJ3B/FWPXKGTIPJZNJ3B.LARGE.jpg?auto=webp&frame=1&width=538&fit=bounds)

Finally, we use an android application developed to control the robot using the Bluetooth module.
At this point, you should have an Automated Navigation Robot that can relay sensor data back to your Android device indicating the environmental conditions around the robot.
