# Tweeting Babbage

## Description
This project is all about making a Twitter bot that can post pictures to your feed at the push of a button. To click pictures it uses the RPi’s camera module, for posting the image clicked there is a separate python script.

The first stage of this project will be taking a picture with the help of the PiCamera module and saving the image file on your Raspberry Pi using a timestamp as a file name.

So to begin with your program should do the following:
* Take a photo using the PiCamera module
* Save the photo using a timestamp as the file name

Following this step, we need to set up a button to trigger it to click a photo using the camera module.

The when_pressed method for the Button class in gpiozero can be used to call any function you have written.

Your first step will be to create a new function called take_photo. Inside this function, you should place code to get the timestamp, save it as a global variable, and take the photo. Then write code to call this function when the button is pressed. Have a look at the steps below if you are unsure about functions or triggering them with buttons.
 
Next, we need to get started with Twitter to tweet photos and text.
To achieve this, you’ll need to make some changes to python script. Below is a list of the elements you’ll need to add or change in your script.

You’re going to want to edit you script so that:
* each time the button is pressed
* not only is the photo taken, but a random phrase is chosen from a list of phrases
* and the phrase and photo are sent to Twitter together.

To send images and text in twitter we use tweepy python module which has built in commands to post text and images. 
 

