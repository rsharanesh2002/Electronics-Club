# Farmaid: Plant Disease Detection Robot

### Problem Statement: 
To make an efficient robot that can traverse through rough terrains of a farm and scan up each of the plants in the farm and detect if the plant has any disease or not?

### Ideation:
The working mechanism for the project is as follows,

**Existing**

_Movement of the robot:_

 Ultrasonic sensor + RPi Camera module => Microcontroller => Motor

_Taking Pictures:_

RPi Camera module => Detect any plant => Take 10 sec video => RPi => Machine learning Model => Results => If disease mark, or else move.

**In Addition**

_Camera Pole Adjustment:_

RPi Camera => AI Model (check if the image covers up whole plant) => Adjust the camera pole => No need Video => Real time classification

_On board Fertilize:r_

Disease detection => Markup the plant => Add fertilizer or medicine on board (if available) => Alert Message


|Process|Idea|Advantage|Disadvantage|
| :---: | :---: | :---: | :--: |
|Movement of the robot|To use the Ultrasonic sensor and RPi camera module to detect any obstacle while moving. We can implement Machine Learning models that are used for self-driving cars.|There won’t be any problem damaging the crops. The movement of the robot will be more efficient.| The complexity of the code will be higher. Also, we need separate RPi to implement it. A lot of Power consumption.|
|Taking the pictures and Pole adjustment|Take a sample picture of the plant and if the whole plant is covered then go for disease detection else adjust the pole height or rotate the camera to cover up the plan, then go for disease detection.|The the whole plant is screened and so the possibility of missing out some affected part of the plant is minimized.|There is a need for some more external hardware and the ML model must also check for the coverage of the whole plant.|
|On Board Fertilizer|To have certain basic fertilizer or Medicinal solutions for treating the disease on the robot and based on the disease some amount of it can be dropped near the root or sprayed up on the plant.|If the disease is a minor one and doesn’t require intensive care then the workman need not waste his time by inspecting that plant.|The fertilizers on board must be handled carefully, and need more hardware for spraying and dripping the fertilizers.|

   The Existing solution is a good one though we can extend it further with the above mentioned functionalities. The robot is not too costly to make, we use just simple dumpyard hardware to make the camera pole and the chassis. One thing to be ensured is that we must make the robot an all terrain rover ( A wheel belt can be used in such a case).

