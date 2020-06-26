# Smart Garbage Monitoring System (Troubleshooting)

***Before diving into troubleshooting Let’s have a quick view of the pipeline***

Level monitoring: Ultrasonic sensor => Microcontroller => Alert to server

Garbage Leveller: Trash Thrown => Compress trash in bin => Level Check

Odour Alert: Odour Sensor => Microcontroller => Alert to server

Spill Alert: RPi camera => Detect spills while throwing => Create alert real-time to the thrower

Solar Powered: Solar panel => Power up the gadgets

***

As you see the pipeline of the whole project is made of four parts, and let’s troubleshoot them individually.

***P.S:*** Also, another important thing to be noted while troubleshooting uis that, once we have done troubleshooting a part,we need to run the complete project again. Because, in most cases we don’t know where the error or the problem is. 

***P.S:*** Another important thing which must be followed is that the wires must be soldered properly and there mustn't be any loose connection. _For this you can use a multimeter and check the connectivity between any two terminals._

***First check if all the modules that we are using are powered up properly (i.e) does the power led in all the modules glows?***
If yes, then the wiring of the circuit is correct in regard to power supply and we are good to go for debugging.

If not, then there might be some shorting of the power supply in the modules, check their working separately and if they work use them, else replace them. For details on their individual working check out the modules section at the end of this doc.
 
 ***
 
Now let’s troubleshoot the First part,

***_Garbage Level Monitoring:_***

This is the first part of the whole system, it comprises two main parts namely the Ultrasonic level sensing and the algorithm in microcontroller to compare the readings with the threshold and send an alert to the user.

***Is your ultrasonic sensor working?***
For that just connect the ultrasonic sensor alone and print the values sensed by it, if it’s fine then the issue is in the code for obstacle detection. The error might be any syntax or typo or in some cases the threshold needs to be changed. Check the code again .If the problem still persists then you can check with the following code for the working of the ultrasonic sensor (connect the pins properly as mentioned in the code),

Code:
```
#define echoPin 2
#define trigPin 3 

long duration;
int distance;

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT); 
  Serial.begin(9600);
  Serial.println("Ultrasonic Sensor HC-SR04 Test"); 
  Serial.println("with Arduino UNO R3");
}
void loop() {
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2; 
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
}
```

If still the problem persists, try changing the ultrasonic sensor.

Now after finishing, just run over this part alone again, you must not return to this afterwards. 

Check the working of the whole thing again.If you were lucky, then you have just made a small error in it. Go on, in testing the product.
 
***Ultrasonic sensor works but there is no alert?***

In this case the error might be in the code that connects the microcontroller to the server. We use the arduino Wi-fi shield and the Arduino MKR100 module for the wireless transmission of the message to the server. If the ultrasonic sensor works fine and there is some issue in this part then you need to check the code that integrates the arduino IOT module and the Blynk App. The major errors can be in the API linking part. Also, be cautious you paste the correct authorization key.

So, in order to solve it, we just use the module separately and check with the Blynk app by writing the sample code to set up a communication channel between them. 
For that do check out this [link](https://www.hackster.io/lintangwisesa/arduino-mkr1000-blynk-e268b0), and then try it.

***

Let’s move on to the next part,

***_Garbage Leveller:_***

In this part the major steps are using the ultrasonic sensor and then the leveller motor to press on the garbage. This work has to be done every time a user throws some garbage in it. For this work we use a metal strip and attached to a hydraulic press. Everytime after the user throws the garbage into it, the motor presses the garbage. The possible issues that might happen it here are 
1. Ultrasonic sensor issue, for this you can follow the same method of troubleshooting as in the above case of level monitor.
2. Hydraulic motors sucks, for this you can simply check the working of the hydraulic press by directly powering it up.

Now after finishing, just run over this part alone again, you must not return to this afterwards. 

Check the working of the whole thing again.If you were lucky, then you have just made a small error in it. Go on, in testing the product.

***

Following this the next part is,

***_Odour Alert:_***

In this part we mainly use the MQ-135 gas sensor, which is mainly used in the detection of hazardous gases. Most probably there won’t be any error in this part. If in case any error occurs then it will be in the connections of the sensor or in the code that connects the MKR1000 to the server. Anyways, we have tested the connection of MKR1000 with the sensor in the above part and so there won’t be any issue. 

So, in order to check the working of MQ-135 sensor, we use the simple code to display it’s reading in the serial monitor,

Code:
```
int sensorValue;
const int rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2;
void setup()
{  
Serial.begin(9600);                            
 }
void loop(){
sensorValue = analogRead(0);       
Serial.print("AirQua=");
Serial.print(sensorValue, DEC);              
Serial.println(" PPM");
delay(100);                                  
}
```

Now after finishing, just run over this part alone again, you must not return to this afterwards. 

Check the working of the whole thing again.If you were lucky, then you have just made a small error in it. Go on, in testing the product.

***

Moving on to the next part,

***_Spill alert:_***

This is a real-time process wherein we use a camera module to capture the real time videos and use it as an input, to an ML model that classifies whether the user has thrown any error or not. The possible error here is the issue with the camera module and the next can be with the ML model (lest case error -might be a small typo in code only). The problem with the ML model can only be with the linking of it with the code of Arduino, if that link was established correctly then there wouldn’t be any issues here.

For the issue with the camera part we can just check out the camera module alone separately and capture some images using it. The tutorial can be found here, the code for it is a pretty longer one.

Now after finishing, just run over this part alone again, you must not return to this afterwards. 

Check the working of the whole thing again.If you were lucky, then you have just made a small error in it. Go on, in testing the product.

Now after finishing, just run over this part alone again, you must not return to this afterwards. 

Check the working of the whole thing again.If you were lucky, then you have just made a small error in it. Go on, in testing the product.

***

Now comes the final part,

***_Solar Powering:_***

This part is pretty much simple, wherein we use a solar panel and then connect it to an adapter and then use it to power up the arduino, we also need a lipo battery in order to store the harvested energy if the arduino isn’t powered. The error that can be made here is only with the connections of the component and other than that no error might occur. So, for resolving it basically check all the connections along with their connectivity using a multimeter as mentioned in th beginning.

## Resources:
1. Blynk and MKR1000 connection : https://www.hackster.io/lintangwisesa/arduino-mkr1000-blynk-e268b0
2. MQ-135 sensor working - https://create.arduino.cc/projecthub/karimmufte/arduino-and-mq-135-gas-sensor-with-arduino-code-a8c1c6
3. OV7670 camera module - https://www.hackster.io/techmirtz/visual-capturing-with-ov7670-on-arduino-069ebb
4. Solar Powering arduino - http://www.cooking-hacks.com/documentation/tutorials/arduino-solar/index.html

