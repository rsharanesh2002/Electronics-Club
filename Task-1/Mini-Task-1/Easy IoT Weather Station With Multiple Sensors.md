# Easy IoT Weather Station With Multiple Sensors
## Description

IoT Weather station collects data from various sensors regarding weather info, integrates them, and then transmits them to a dashboard and visualizes the results. In order to do that we first begin with the microcontroller which we here use NodeMCU. The IoT dashboard which we use to view the data here is the Thingspeak channel.

Here we stream the following sensor data to a Thingspeak channel:

* Temperature DHT11/22;
* Temperature BMP180;
* Humidity DHT11/22;
* Pressure BMP180;
* Dew point temperature DHT11/22;
* Altitude BMP180;
* Light intensity LDR;
* Rain value.

Following this, we need to wire up all the sensors to NodeMCU and check their working individually. If they work properly then we connect all the sensors and move on further. The main advantage of using NodeMCU is that it looks more similar to that of an Arduino, also it's programming can be completely done by using an Arduino.

As we are going to push our data to Thingspeak we have to make an account. Thingspeak is a cloud service. It is great, easy, and looks really cool! Next to this, Thingspeak provides several options for interaction with your data such as Thingtweet, Thinghttp, etc. 

Simply go to thingspeak.com and make an account. Next, we must start adding fields to receive data transmitted by NodeMCU, the number of fields depends on the number of sensors we use. You can find a key that you have to mention in your Arduino sketch under the tap 'API key'. This key is necessary to connect the Arduino to the Thingspeak channel. 

The next thing is to code the NodeMCU to collect data from all the sensors and transmit it to the dashboard using the unique API key generated. That’s it the IoT Weather Station using NodeMCU is ready.

## Project Image

![](https://cdn.instructables.com/F4D/602U/IOH8N390/F4D602UIOH8N390.LARGE.jpg?auto=webp&frame=1&width=937&height=1024&fit=bounds)


