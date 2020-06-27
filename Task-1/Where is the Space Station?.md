# Where is the Space Station?

## Description

This project is all about using a web service to find out the current location of the International Space Station (ISS) and plot its location on a map. The web service that is used here has an address (URL) just like a website does and instead of returning HTML for a web page, it returns data in the json format. The data returned by the web service is live data. We call this web service from the python script. In python the data retrieved is in the format of a dictionary. After then we can use this dictionary to process the information. 

The International Space Station is in orbit around Earth. It completes an orbit of the earth roughly every hour and a half, and travels at an average speed of 7.66 km per second. There is another web service that provides the location of ISS in the same json format.

The location of ISS is provided in the format of latitude and longitude. To plot the location of ISS on the map, we use turtle library and import the map module, and use the latitude and longitude to plot the location of ISS.

Now, to show time at which ISS will cross a particular location, there is another web service which gives out the next time at which it will cross over at the particular location. 

Now, we integrate all these in the map created using turtle and display them in real time.
