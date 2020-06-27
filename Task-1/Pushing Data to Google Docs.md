# Pushing Data to Google Docs
## Description
Push mechanism of storing the data from hardware in google sheets sends a request with data to a Google server running a script that will, in turn, store that data received in a Google spreadsheet. There is even another mechanism called the 
Poll mechanism. 

**The project involves the following tasks to be done:**
* A Google Sheet with labels at the top of each column where your data will go.
* A Google Javascript that controls the behavior of the Sheet. The tutorial links to a page that shows how to do this. The script will be deployed as a web app that gets hit by your webhook.
* Particle firmware which publishes JSON strings like this:{variable name: value other variables: value2}
* A webhook which hits your Google Web App, is web form type, with query parameters like this:{GoogleSheetLabel1: {{variable name}}GoogleSheetLabel2: {{other variable}}}

**To set up the hardware to push data to google sheets via the particle cloud, we need two things:**
* configure a webhook
* code a publish command in your firmware to trigger that webhook with the wanted information

![](https://hackster.imgix.net/uploads/attachments/179229/ParticleCloudGoogle.png?auto=compress%2Cformat&w=680&h=510&fit=max)

## Push Versus Poll
In the poll mechanism, as described in my previous article, the Google spreadsheet runs a script that sends a request to fetch data from our hardware at a regular interval.

You can use the poll mechanism when your hardware is online all the time, for instance, to capture sensor data that changes slowly over time (for example: the temperature of your pool).

In the push mechanism, described in the current article, your hardware sends a request with data to a Google server running a script that will, in turn, store that data received in a Google spreadsheet.

The push mechanism is ideal when your hardware might be sleeping from time to time (hence not reachable), to capture a specific event (example: your garage door is opening) or to store a log of what your hardware is doing.

