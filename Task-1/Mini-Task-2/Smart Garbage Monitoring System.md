# Smart Garbage Monitoring System

### Problem Statement
To make a smart Garbage monitoring system using IOT to monitor the level of garbage in the bins in a locality.

### Ideation
The working mechanism of the project is as follows,

**Existing:**

_Level monitoring_

Ultrasonic sensor => Microcontroller => Alert to server

**In Addition:**

_Garbage Leveller_

Trash Thrown => Compress trash in bin => Level Check
 
_Odour Alert_

Odour Sensor => Microcontroller => Alert to server

_Spill Alert_

RPi camera => Detect spills while throwing => Create alert real-time to the thrower

_Solar Powered_

Solar panel => Power up the gadgets
	


|Process/Sensor|Idea|Advantages|Disadvantages|
|:----:|:----:|:----:|:----:|
|Garbage Level Monitoring|To use an ultrasonic sensor at the lid of the garbage bin and detect the amount of trash filled in it and send it real time to the server.|The work of the collector is reduced, if it’s filled only he could reach that location to collect the trash.|The ultrasonic sensor always doesn’t provide the exact level,it’s accuracy is low so a garbage leveller must be used.|
|Garbage Leveller|To use a leveller(in specific a steel plate) to press on the garbage to compress it to its maximum level. so that more thrash can be added into it.|If the added garbage is compressed (levelled) then more thrash can be put into it and the over-spilling can be reduced.|Hardware cost. Should use Pneumatics a bit costlier.|
|Odour Alert|To use an odour sensor in order to monitor the odour of the garbage bin and give alert to the collector if there is any hazardous gas detected.|Can reduce the smell of bins on the roadside.|Cool sensor to use. No cons.|
|MQ-135 Sensor|The MQ-135 Gas sensors are used in air quality control equipment and are suitable for detecting hazardous gases. The MQ-135 sensor module comes with a Digital Pin which makes this sensor to operate even without a microcontroller. If you need to measure the gases in PPM the analog pin needs to be used. The analog pin is TTL driven and works on 5V and so can be used with most common microcontrollers.|An easy to use a sensor that gives us the quality of the air in terms of PPM. The sensor can be fitted inside the bin to find the PPM of the gases inside it.|Cool sensor!!|
|Spill alert|We could use either an ultrasonic sensor or the RPi camera module in order to detect if the bin user throws some waste outside the bin and create an alert to the user to throw it in the bin properly.|It will keep the surroundings of the bin to be kept clean.|It will increase the sensor cost and also the complexity of the code written to detect the spillage.|
|Solar Powering|To use solar panels to harness solar energy and use it to power the electronics sub-systems in it.| Reduces the cost of power management and also makes the device more eco-friendly|Solar panel costs a bit.|

The idea of the project is to use the Ultrasonic sensor to detect the garbage level and level it before detecting. It uses odour sensors to detect any hazardous sensors and transmit it in real time to an app. Also it detects for any spillage while any user throws garbage in the bin and notifies them to throw it properly. 
