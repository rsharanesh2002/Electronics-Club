# Real-Time 2G/3G/LTE Arduino GPS Tracker + IoT Dashboard
## Description
This is a GPS tracker using the Botletics SIM7000 LTE shield and an Arduino and views the data on two free IoT dashboards.
The Boltetics SIM7000 LTE shield is low-power modules that support the new LTE CAT-M1 and NB-IoT technology and also have integrated GNSS (GPS, GLONASS and BeiDou/Compass, Galileo, QZSS standards) for location tracking. The shield also supports an MCP9808 I2C temperature sensor, great for at least measuring something and sending it via a cellular connection.
The two dashboards are Freeboard.io and ThingsBoard.io.These are free IOT dashboards that are user-friendly and easy to use, with quick navigation. We basically create panes for each of the data which is being accessed. To do it in an easy manner, the both have drag and drop features.
## FreeBoard.io 
Freeboard.io is a cool IoT dashboard that can connect with numerous cloud platforms like PubNub and dweet, as well as other features like JSON and MQTT. As you probably have guessed we'll be also using dweet.io which is used in the example code from the previous section. As an important note, dragging panes in freeboard.io doesn't seem to work in Chrome so use Firebox or Microsoft Edge instead.
## ThingsBoard.io 
ThingsBoard is an open-source IoT platform for data collection, processing, visualization, and device management. It enables device connectivity via industry standard IoT protocols - MQTT, CoAP, and HTTP and supports both cloud and on-premises deployments. ThingsBoard combines scalability, fault-tolerance, and performance so you will never lose your data.
## What is LTE CAT-M?
LTE CAT-M1 is considered the second-generation LTE technology and is lower-power and more suitable for IoT devices. NarrowBand IoT (NB-IoT) technology is a Low-Power Wide Area Network (LPWAN) technology specifically designed for low-power IoT devices. 
LTE CAT-M has certain tradeoffs, large bandwidth allows devices to send lots of data (like your phone, which can stream YouTube!) but this also means it's very power-hungry. Increasing the range (the "area" of the network) also increases power consumption. In the case of NB-IoT, cutting down the bandwidth means that you won't be able to send much data, but for IoT devices shooting morsels of data to the cloud, this is perfect! Hence, "narrow"-band technology, ideal for low-power devices with little amounts of data but still with long-range (wide area)! Additionally, NB-IoT is designed for deep building penetration which could be perfect for commercial IoT devices.

## Project Image

**Freeboard.io results-**
![](https://hackster.imgix.net/uploads/attachments/401105/road_test_data_qlcuythJNb.PNG?auto=compress%2Cformat&w=680&h=510&fit=max)

**Thingsboard.io Results-**
![](https://hackster.imgix.net/uploads/attachments/401127/road_test_data_1_tjcsN4SMWa.PNG?auto=compress%2Cformat&w=680&h=510&fit=max)
