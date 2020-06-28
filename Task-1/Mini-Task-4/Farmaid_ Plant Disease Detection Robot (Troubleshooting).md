# Farmaid: Plant Disease Detection Robot (Troubleshooting)

Before diving into troubleshooting Let’s have a quick view of the pipeline

_Movement of the robot:_ Ultrasonic sensor + RPi Camera module => Microcontroller => Motor

_Taking Pictures:_ RPi Camera module => Detect any plant => Take 10 sec video => RPi => Machine learning Model => Results => If disease mark, or else move.

_Camera Pole Adjustment:_ RPi Camera => AI Model (check if the image covers up whole plant) => Adjust the camera pole => No need Video => Real time classification

_On board Fertilizer:_ Disease detection => Markup the plant => Add fertilizer or medicine on board (if available) => Alert Message

***

As you see the pipeline of the whole project is made of four parts, and let’s troubleshoot them individually.

**P.S:** Also, another important thing to be noted while troubleshooting uis that, once we have done troubleshooting a part,we need to run the complete project again. Because, in most cases we don’t know where the error or the problem is. 

**P.S:** Another important thing which must be followed is that the wires must be soldered properly and there mustn't be any loose connection. _For this you can use a multimeter and check the connectivity between any two terminals._

***First check if all the modules that we are using are powered up properly (i.e) does the power led in all the modules glows?***

If yes, then the wiring of the circuit is correct in regard to power supply and we are good to go for debugging.

If not, then there might be some shorting of the power supply in the modules, check their working separately and if they work use them, else replace them. For details on their individual working check out the modules section at the end of this doc.

***

Now, let’s troubleshoot the motor part,

_***Movement of the robot :***_

So, let’s first upload a simple code used to test the working of a motor. For that try writing code setting l1 HIGH and l2 LOW and check if the motors rotate. Because if it doesn't, then the problem is usually with the Motor driver and a motor driver can be destroyed easily. So , make sure you don't short it / Power it on before checking your circuit twice. 

Code :
```
int l1 = 6;
int r1 = 5;
int l2 = 4;
int r2 = 3;

void setup() {
  
  delay(500);
  Serial.begin(9600);
  pinMode(l1, OUTPUT);
  pinMode(l2, OUTPUT);
  pinMode(r1, OUTPUT);
  pinMode(r2, OUTPUT);
  digitalWrite(l1, HIGH);
  digitalWrite(r1, HIGH);
  digitalWrite(l2, LOW);
  digitalWrite(r2, LOW);
}

void loop() {
}
```

**Is the robot moving,or even at least the motors of the robot are rotating ?**

If yes, then there is no problem with the movement of the robot and so you may move on to the next part of the pipeline. 

If not then the problem may be in any of the following, either in the motor driver we use to drive the motors or in the ultrasonic sensor/camera module which are used to avoid obstacles, there might be some error so that they always output that there is an obstacle. So, again go back and check the sample code above to test only the rotation of the motor. Also, check if there were any loose connections. If the motor alone works perfectly without connecting it with the ultrasonic sensor, then the problem is for sure in the logical part of writing the code for the obstacle avoidance. 

***Then you can check if the ultrasonic sensor is working properly or not?***
For that just connect the ultrasonic sensor alone and print the values sensed by it, if it’s fine then the issue is in the code for obstacle detection. The error might be any syntax or typo or in some cases the threshold needs to be changed. Check the code again . If still the problem persists, try changing the ultrasonic sensor. If the problem still persists then you can check with the following code for the working of the ultrasonic sensor (connect the pins properly as mentioned in the code),

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

Now after finishing, just run over this part alone again, you must not return to this afterwards. 
Check the working of the whole thing again.If you were lucky, then you have just made a small error in it. Go on, in testing the product.

***

Moving on to the next part, 

***_Camera Pole adjustment:_***

***Is atleast the Camera module powered?***
If the camera module isn’t powered then there might be some connection problems in the power supply, do check if the wires are connected properly.
If not (i.e) the module is being powered up but the pictures aren’t taken, then I am pretty much sure that the error must be in the coding for the camera module. So, do check the modules part and sort out the code).

Same as we did above, we will just test this part of the project alone separately and find out the errors. For that we just connect the camera module of RPi to RPi and just upload the sample code to check if pictures are taken? 

Code:
```
from picamera import PiCamera
from time import sleep

camera = PiCamera()

camera.start_preview()
sleep(5)
camera.stop_preview()
```
Once you run the code then you must actually see the camera module just starts for 5 seconds and stops, if it does so then there isn’t any problem with the camera module. Else you need to change the camera module itself.

Then check with this code, if you run this code then a picture must be captured and saved in the shown path in your RPi. 

Code:
```
from picamera import PiCamera
from time import sleep

camera = PiCamera()

camera.start_preview()
sleep(5)
camera.capture('/home/pi/Desktop/image.jpg')
camera.stop_preview()
```

If the pictures are captured and they can be viewed on the screen, then we are good to go and you can proceed further on.

If not, then there is some error in the camera module or in the RPi. Before looking onto the error make sure that you have the latest version of the Pi Camera library installed and also the camera module is being powered up.

The most common errors are Unable to connect to the RPi camera, If you are getting this error message, then you likely forgot to 
1. run raspi-config, 

2. enable the camera, and 

3. reboot your Pi

and the Truncate error, these  errors are fairly easy to identify since they always end with the text  Incorrect buffer length for resolution, If you are getting this error message, you likely forgot to call .truncate  after you were done processing your frame. In short, Go back to your script and ensure you have called .truncate  before .capture(to capture the video)  is called again.

Now after finishing, just run over this part alone again, you must not return to this afterwards.
	
***Pictures are taken but no output for adjustment of the camera pole?***
The design of our system is that initially, the Camera module initially takes a picture and sends it the OpenCV model to detect if the complete plant is being covered up by the camera or not. Further based on the response form the model we decide on whether to adjust the pole.

If such a situation occurs wherein the pictures are taken and there is no output, the error can be in the following ways 1) The motor trying to adjust the pole should have sucked up or 2) there might be some implementational error in the OpenCV model. 

So, to sort out the first issue, we just drive the motor separately as we did in the first part and check it’s working. If it worked then the problem is surely in the algorithm. If not then try changing the motor/motor driver used here.
The second issue can be resolved by looking at any error in the OpenCV model. To find out the issue we can test the built model separately using a single image rather checking with the real time images. 

***P.S:*** If you’re using Python virtual  environments, you’ll want to use the workon  command to switch to the Python environment that has your OpenCV + picamera library installed.

Now after finishing, just run over this part alone again, you must not return to this afterwards. 
Check the working of the whole thing again.If you were lucky, then you have just made a small error in it and you have corrected them. Go on, in testing the product.

***

Moving to the main important part of our project,

***Taking videos and the Main algorithm:***

Actually we have tested our camera in the previous part itself and so I guess there won't be any error in this part pertaining to the Camera module. If it were so then it must be a simple syntax error or just a typo. 
The actual problem will be from the main ML model we use which is the MobileNet SSD model. So, to sort out the issue, we basically do the same we did earlier in the case of the OpenCV model. Pull out the model separately and just take a real time picture and then predict it with the help of the model. If it does the classification properly then the problem will be with the linking process of the other parts with each other. For this issue the syntax of the connecting statements must be double verified.

Now after finishing, just run over this part alone again, you must not return to this afterwards. 
Check the working of the whole thing again.If you were lucky, then you have just made a small error in it and you have corrected them. Go on, in testing the product.

***

Moving on to our final part,

_***On-Board Fertilizer:***_
If all the above parts work properly then there won’t be any issue in this part of the project. This is a pretty much simpler one as compared to the others.
Another important task for the robot is to spray the fertilizer (basic ones) to the plant that doesn't need other human work to be done. For that purpose, based on the classification made by the model, we use a sprinkler and a motor pump to spray the fertilizer on the plant. 

The possible issues here are
1. The Fertilizer level monitor cups, we use another ultrasonic sensor to monitor the level of  the fertilizer in the on-board tank and so if there are any issues here, do the same procedure as we did for the one used in the motor mobility.
2. The motor pump/ sprinkler stops working, there is no explicit reason for it, it might be due to some technical fault within them and the only way for it to replace them.


## Modules:
1. Motor Driver Troubleshooting : https://roboindia.com/tutorials/motor-driver-arduino/
2. RPi camera (getting started): https://projects.raspberrypi.org/en/projects/getting-started-with-picamera/6
3. RPi camera trouble video: https://youtu.be/GImeVqHQzsE
4. Camera Errors: https://www.pyimagesearch.com/2016/08/29/common-errors-using-the-raspberry-pi-camera-module/



