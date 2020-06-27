# Pool Controller


## Description

Usually, the pool controls simply used an age old-timers, which often get damaged and incur more cost of repairing. So, in order to solve this issue this project comes up with an automatic pool controller by not just using a timer, it makes decisions by considering the various factors affecting the pool environment. It utilizes a Raspberry Pi running Windows 10 IoT Core, Relays, Arduino Mini Pro, as well as temperature sensors, wiring, and 3D, printed components.
 
The project first controls solid-state relays using Raspberry Pi running Windows 10 IoT Core. These relays allow us to control the AC (Alternating Current) components such as the pool pump.  The solid-state relays control the existing 30Amp AC relays that the old-timer had utilized.  After this, we added the controller functionality for the other components such as pool waterfall, and my pool and yard lights.
 
Then we build a headless Windows 10 IoT Core Background Application that acts as a simple HTTP Web Server responding to HTTP GET and POST requests. 
 
Finally, an HTML control program is built that will run on virtually any device. This allows us not only to control the pool pump, waterfall, and pool lights but also to monitor the additional sensors from anywhere.

## Project image
![](https://hackster.imgix.net/uploads/image/file/76350/PoolControllerHTML.png?auto=compress%2Cformat&w=680&h=510&fit=max)
![](https://hackster.imgix.net/uploads/image/file/76351/OpenHABUI.png?auto=compress%2Cformat&w=680&h=510&fit=max)

 

