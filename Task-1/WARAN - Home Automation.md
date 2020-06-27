# WARAN - Home Automation
## Description
WARAN (Windows IoT, Azure, Raspberry Pi, Arduino, NRF24L01+) is a modular home automation system which consists of a single Hub and multiple modules. The module will be a combination of microcontroller and sensors collecting data from different locations of the house and transmitting the data to Hub via RF. All the communication between Hub and modules happens via RF. There will be a companion windows phone app for the Hub as well. 
### Flowchart
![](https://hackster.imgix.net/uploads/image/file/75917/waran_flow.png?auto=compress%2Cformat&w=680&h=510&fit=max)
 
 

## Why NRF24L01+ ?
Among the wireless options available, NRF24L01+ came up as a cheap and low power consuming solution, with some really powerful libraries available in it.
## The Hub
The Hub is a controlling center of WARAN. It is made up of RPI2, Arduino Uno, and nRF24L01+. The RPI2 runs Windows IoT core. It runs a Universal App which acts as the control center. The Hub would be connected to a large display (typically a TV or monitor) via which we can see the data from the modules and also control the modules. A keyboard and mouse connected to the RPI2 will help in adding, removing modules from the control center. 
Every module will have a unique address using which the hub communicates with it. We will add a module to the control center using this address and giving a name to the module. Once added the control center (Universal App) will send data to Arduino Uno via I2C. Arduino Uno will send data to the module via nRF24L01+ and the module reads data from the sensors or start/stop a device based on the data it received and sends data back to Arduino Uno. The Arduino Uno will send the data to the control center via I2C. This data will be displayed in the TV/Monitor and also sent to cloud. The Arduino Uno will just act as an interface for RPI2 to get the sensor data from other modules. The above process will happen in three scenarios
* At specific intervals depending on the module
* When a user interacts with control center (via Mouse/Keyboard)
* When a trigger is sent from the cloud (vis PubNub)
![](https://hackster.imgix.net/uploads/image/file/76649/waran_hub_module_flow.png?auto=compress%2Cformat&w=680&h=510&fit=max)

## The Control Center
The control center is a universal app running in the RPI2. The control center is the interface for the user to interact with. It communicates with the modules and also with the cloud. WARAN control center utilizes Azure Mobile Services and PubNub as its cloud back-end. Every module-info we add will be stored locally in SQLite DB and also sent to azure mobile service. This will, in turn, send a PubNub message or push notification to the mobile app.

## The Mobile App
The mobile app is a windows phone app (will be developing for other platforms later) which will act as a companion app to the hub. We can see all sensor-related data in the mobile anywhere from the world. If any important information is obtained from the module (like an alert for a gas leak from a gas leak monitor module) we will get a push notification as well. Also, we can trigger some action on the module (like starting a pump on the Plant Waterer module) from the mobile itself. Since all these happen via cloud there is no need for a mobile device to be present anywhere near the hub to do all these actions.

 
## Modules
The module is a combination of components working together and receiving and sending data to and from Hub via RF. It can be a combination like Arduino Pro Mini with sensors or RPI2 with sensors etc. All it needs to do is receive the data/command from the hub via RF and respond appropriately. This gives an infinite possibility of modules.

