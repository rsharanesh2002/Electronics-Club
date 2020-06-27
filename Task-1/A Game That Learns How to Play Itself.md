# A Game That Learns How to Play Itself
## Description
This is a game that learns to play on itself after several times of playing. This is implemented using Neural networks that make the gameplay itself. The software here used is the Unity Game engine that itself has ML agents to use neural networks along with the game. The game that is being played here is the ball balancing one, which requires simple hardware only to be built since the number of variables, in this case, is very less.

Now, in order to create the hardware, we use an old joystick along with two servos with a rod that moves the joystick’s control. These two servo motors are being controlled using an Arduino nano. 

Next comes the game development, the task of the game is to balance the ball on an oscillating platform (platform oscillates as per the joystick input) at the target site marked on the platform.

Finally, we enter the ML model, which is the heart of the project. The following steps happen during training:
the AI, let's call it an agent, looks at the state of the game (observation), where it collects the information directly in-game. It looks for the speed and location of the ball and also the angle of the platform, following its observations, it will take an action (move the joystick), depending on the outcome of this action, it will either receive punishment if the ball falls (negative score) or a reward (positive score) if the ball remains on the platform, the closer the ball is to the target the bigger the reward is, also along with the reward is given for the smooth play.
