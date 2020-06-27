## EE04: Project Meeting -2 (June 13, 2020) (5:30-6:50 pm)

**Praveen:**

Praveen explained about trello's usage, the EE04 board and the lists in it. The lists in it are Questions to be discussed in the meeting (the question to be discussed in the upcoming meeting), meetings (contains the MoM of all the meetings), Project tasks (the upcoming and the backlog tasks). In the last praveen discussed about the current situation of lockdown in terms of project work. As we are in the ideation part, we won't we affected much. Anyways if the exam schedule is out, then time will be given for acads. Also, the current time can too be used for acds. Other mention was regarding Open house being shifted to the even semester.

**Aswin:**

The members started explaining about their project ideation individually one by one. 
Ruban statrted to explain his project ideation first, his idea was to use sensors only inside the pen. He used BMP180 pressure sensor at the nib of the pen and a IMU sensor (MPU6050 - 6 DOF) to track the movements of the pen (his arguement was that writing using a pen is nothing but a kinetic motion of the pen). Also he had an idea to use a erase button to remove the recent word typed. 

Then sagnik presented his presentation, where he applied the principle of a optical mouse to track the exact location of the pen in a platform. He used a ADNS-2620 Optical Mouse Sensor IC, that is used in optical mouse. It captures images at around 1500 frames per second, and the light refected is used to track the location. 

Following it was swathi's presentation, where she first classified the problem as a tactial SLAM problem. She tried with normal IMU sensor but due to drift error in it that multiplies and exponentiates, so she found out other sensor called the Timing IMU sensor that shall ease the problem, but they were withdrawn from production. So she used a 10 DOF IMU (including pressure sensor builtin), and a GPS module to locate the position of the pen.

Finally, sharanesh presented his idea of using only sensors outside the pen, rather within the pen. To remove unwanted words that were detected he used a pressure sensor and a tilt sensor so as to activate the outside sensors to start sensing the data. The sensors that were placed outside were the series of IR sensors. He inspired this from the sony experia touch gadget, that does the same but in a different application. 

Following this the queries were asked on each idea and then Aswin commented on each of the idea individually regarding the pro's and con's of each of it. Looking at Ruban's and Swathi's idea the main problem in them is to reduce the drift error created in the output of the IMU sensor. Coming to sagnik's idea, the issue was with the spacing to be generated when we move to a next word or a next line. If we use a optical sensor, then it's kind of based on relative positioning, so if we need to move to a new line the pen get's confused with no sufficient data. So, there was a suggestion to combine the both of two ideas, IMU and optical mouse to comabt this issue. Looking at sharanesh's idea there wasn't any need for sensors inside the pen, if we are using series of IR sensors outside the pen. We coiuld program the pen so that it detects only the movement of nib, and excludig the other readings (Since nib is very thin, one/two IR sensors will only activate). But this entirely a new category wherein sensors are only placed outside the pen.

Finally the whole idea was made into two broad categories, use all sensors inside the pen and the other is to use all the sensors outside the pen. Follow up tasks will be given separately to this two categories and we try with both the models and find their individual accuracy and then decide on which has to be used exactly.Aswin also added that if we can combine the both ideas, then the accuracy could be improved further.
