# DIY Arduino + GY-906 Infrared Thermometer
## Description
The infrared thermometer can measure the surface temperature of an object. Its advantage is non-contact temperature measurement, which can conveniently and accurately measure the temperature of a remote object.
It uses the GY-906 infrared thermometer sensor. This module is very cheap, easy to integrate, and supports an I2C interface with a 10K pull-up resistor. The factory calibration of this temperature sensor is: the sensor temperature range is -40 to 125 degrees Celsius, and the object temperature range is -70 to 380 degrees Celsius. The error range of the sensor is about 0.5 degrees Celsius.
Also to display the Temperature measured by the sensor we use an OLED Display to display it

## GY-906 MLX90614 Infrared Sensor
The MLX90614 is an infrared thermometer for non-contact temperature measurements. Both the IR sensitive thermopile detector chip and the signal conditioning ASIC are integrated into the same TO-39 can. Integrated into the MLX90614 are a low noise amplifier, 17-bit ADC, and powerful DSP unit thus achieving high accuracy and resolution of the thermometer.
The thermometer comes factory calibrated with a digital SMBus output(The System Management Bus is a single-ended simple two-wire bus for the purpose of lightweight communication. Most commonly it is found in computer motherboards for communication with the power source for ON/OFF instructions.) giving full access to the measured temperature in the complete temperature range(s) with a resolution of 0.02°C.
The user can configure the digital output to be pulse width modulation (PWM). As a standard, the 10-bit PWM is configured to continuously transmit the measured temperature in the range of -20 to 120°C, with an output resolution of 0.14°C.

## The Working Principle of Infrared Thermometer
The infrared thermometer consists of the optical system, photodetector, signal amplifier, signal processing, and display output. The radiation of the measured object and the feedback source is adjusted according to the modulator and input to the infrared detector. The difference between the two signals is amplified by the inverse amplifier and the temperature of the feedback source is controlled so that the spectral radiance of the feedback source is the same as that of the object. The display indicates the brightness temperature of the object being measured.

## I2C Serial Communication Protocol
I2C combines the best features of SPI and UARTs. With I2C, you can connect multiple slaves to a single master (like SPI) and you can have multiple masters controlling single, or multiple slaves. This is really useful when you want to have more than one micro-controller logging data to a single memory card or displaying text to a single LCD.
Like UART communication, I2C only uses two wires to transmit data between devices:
SDA (Serial Data) – The line for the master and slave to send and receive data.
SCL (Serial Clock) – The line that carries the clock signal.
I2C is a serial communication protocol, so data is transferred bit by bit along a single wire (the SDA line).
Like SPI, I2C is synchronous, so the output of bits is synchronized to the sampling of bits by a clock signal shared between the master and the slave. The clock signal is always controlled by the master.

## Project Image
![](https://hackster.imgix.net/uploads/attachments/1104209/image_psflkK34Oh.png?auto=compress%2Cformat&w=680&h=510&fit=max)
 

