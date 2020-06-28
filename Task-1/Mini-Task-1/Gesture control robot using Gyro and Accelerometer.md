# Gesture control robot using Gyro and Accelerometer

## Description
This project is all about, to make a gesture-controlled robot using an Accelerometer cum Gyro sensor. A 3-axis accelerometer cum gyro sensor MPU-6050 is placed on the user's hand on a glove, by using this sensor the movement of the hand and the acceleration of movement in that direction could be retrieved. Following this, a Bluetooth module on the glove is used as a transmitter (master) to transmit the sensor data to the robot. To perform this task an Arduino nano is used which is placed on the glove itself.

In the robot, we use an Arduino and other Bluetooth module which acts as a receiver (slave) in this case and receives the sensor data, and Arduino processes the data. Now As per the data received the movement of the robot is decided.

The important task here is to configure the two HC-05 Bluetooth modules independently, one to act as master and others to act as a slave. To do that we use the AT Commands by connecting the Bluetooth module to Arduino and then using the serial monitor to send out the commands.


## Configuring the Bluetooth module 
HC-05 Bluetooth module comes with a slave module factory setting, which means we can send data to the module just by plugging it in, no need to do any other setting to send data from mobile devices to the HC-05 module. Just enter its default password (1234/0000)to connect it with. But if we want to send data using this module to some other same module or to a mobile device then we need to configure it.

We use two Bluetooth modules here, one on the hand to transmit and other on the robot to receive the data. First, we need to configure two Bluetooth modules, so that they can automatically bind with each other after power on. Here the which module is acting as a slave device, will receive signals from the remote unit and will be mounted on the car. And the second one acts as a master device which will act as transmitter units and will send data to the slave device.

So to configure the Bluetooth module as a slave device, connect it with Arduino as per this wiring diagram.
![](https://hackster.imgix.net/uploads/attachments/999486/SnapshotDADA_-_6.png?auto=compress%2Cformat&w=680&h=510&fit=max)

Disconnect the module, press and hold the key on the module and connect it back. You will see the led on the module is blinking slower. Once every 2 seconds. This means HC-05 is in the AT command mode. Now open the serial monitor, change the baud rate to 9600, and output type as both NL & CR. Now type AT in the send box and send it, if it replies with ok, it means all Is well. If not then try again. 

Now send the following commands,

AT+ORGL and send it. this command will set the module in the factory setting.

AT+RMAAD this command will release module from any previous pairing

AT+UART? check the current baud rate of the module

AT+UART=38400, 0, 0 set the baud rate as 38400

AT+ROLE? check the role whether it is slave or master. it replies with 0 or 1. if the module is a slave it replies 0 and if it is a master device then it will reply with 1

set role as a slave device. enter AT+ROLE=0

AT+ADDR? check the module address.

Note down this address replied by the module, after getting this address the configuration for the slave module is done.

 
Now it's time to configure the second Bluetooth module as a master device. Connect this module with the Arduino board and enter it into the AT mode. Then enter these AT commands by the given sequence.

AT+ORGL

AT+RMAAD

AT+UART?

AT+UART=38400, 0, 0

AT+ROLE?

set the role of this module as the master device. AT+ROLE=1

AT+CMODE=0 so that the module will connect only to a single device, the default setting is 0

now bind this module with a slave device to do this enter,
AT+BIND=" the address of the slave module" 

Now, everything is done and we have successfully configured both the Bluetooth modules.

 
