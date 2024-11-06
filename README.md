# Arduino UI for Embedded Systems Project at Defang Software Labs (Wifi)
*Note: This repository version involves wifi networking. For the static (non-networking) version of this project, please see the `/defang-arduino-static` repository [here](https://github.com/commit111/defang-arduino-static).*

![project image](./images/wifi.png)

This repository contains an interactive wifi-connected UI program for a [SenseCAP Indicator Device](https://wiki.seeedstudio.com/Sensor/SenseCAP/SenseCAP_Indicator/Get_started_with_SenseCAP_Indicator/), built for an Embedded Systems project at Defang Software Labs.

The device has a square liquid-crystal touch screen display, and a ESP32-S3 chip that can be programmed in an Arduino environment.

The program `welcome.ino`, acting as a client, pings data every 5 seconds after it is connected to a wifi network. It uses a library called [ArduinoHTTPClient](https://github.com/arduino-libraries/ArduinoHttpClient). It is also recommended to use [Arduino IDE](https://www.arduino.cc/en/software) when coding with `.ino` files. The program UI will display a message that is randomized in color and location on the screen at the same time during pings (every 5 seconds). 

The Flask server in `web_server.py` receives these pings when it is initialized and connected to the same wifi network as the client. To initalize it, run `python web_server.py`. To view it, open `localhost` with the port number used. To deploy it to the cloud, run `defang up` in the `\welcome` directory.

A helpful file called `serial_reader.py` decodes serial monitor readings to a readable format, allowing you to see `Serial.println()` messages in real time when running.  To initalize it, run `python serial_reader.py` and see it show up in the terminal. 

