Hello this is the configuration for how I am running 2 fermentation chambers using ESPHome and Home Assistant.

The whole controller is run via a 12v power plug which then feeds a buck boost coverter to bring the power down to the 3v3 needed for the ESP32. I opted to have 12v brought into the enclosure as the 12 v is used to run the fans.

This specific setup uses a Kasa HS300 power strip to control the power going to the "refrigerators" and heaters. The fans for the two fermentation chambers are managed via mosfets which are driven by GPIO pins. 
Using this code as a base, you could also just run the fans off the power strip as well, as the HS300 has 6 total outlets.

The display used is a generic 4x20 i2c screen.

In my code the two fermentation chambers are named Brown and Keg. Feel free to change these variables as needed, however be sure to change the names of all affiliated variables such as switches, temp sensors, and output plugs.

There is an additional automation file which must be set up in Home Assistant to turn off all the plugs if the temp sensor is ever not detected or unavailable to keep from damaging your equipment. If you opt to run your hardware directly off GPIO pins you will not need this file.
