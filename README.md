# Garage-Door-Controller-Arduino
A simple Arduino project where you can use a generic ESP8266 board and up to 4 relays where you can control your garage port via a web GUI.

#### Overview
The schematic for the project is provided in the schimatic.jpg above, but Ill write down the important parts below:

Relay 1-3 uses the digital port 0-2, and the relay nr. 4 uses digital port 5. This is because there are some special ports in between port 2 and 5, like 'flash' port, ground and 3.3v ports.

One more important thing is that the relay that I choose runs on 5v and the ESP8266 is only 3.3v, so to make this work the relay needs to be powered via the 'RSV' port, it will have the same power output as your power input, which will be enough to power the relay.

#### Parts
I've just used a regular generic ESP8266 module as controller for this project with a Geekcreit 4 relay module. 

#### Customization
You can customize this controller just as you want, the index.html file provided is the GUI, and you can put your name/company name on top, change the background and do whetever you want. To insert your customized index.html page into the controller you need to transform the contents of the index.html to a single line, and then insert it into the `handleRoot` method.

To customize the internal URL/DNS name of the controller you need to change the `MDNS.begin` in the code from 'garaget' to whatever fits you the best. Then you can access the controller in your browser with 'http://garaget.local'.

