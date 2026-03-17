Based on info from https://github.com/dracoventions/TWCManager/issues/20 I made, with the help of the AI Claude, an ESPHome yaml to search my network for a HomeWizard p1 meter and use that data to emulate a Neurio Energy Meter, thereby adding load balancing to my Tesla Wall Connector 3.
Claude's work still needed a lot of attention. In the end, it took me about 25 iterations before I manually resolved the rest.
<br>
<br>**Hardware**<br>
For this I used the following hardware.
<br>
esp32-s3-devkitc-1 n16r8 (https://nl.aliexpress.com/item/1005010579778226.html) and RS485 to serial module (https://nl.aliexpress.com/item/1005010275911984.html).
<br>But knowing what I know now, I would have ordered this RS485 to serial module: https://nl.aliexpress.com/item/1005008635626105.html.
<br> 
<br>
This is what it looks like after the parts have been soldered together:
<br>
<img width="1421" height="325" alt="{E771A27B-CB0E-4071-BEE7-58BBA7FE2A7C}" src="https://github.com/user-attachments/assets/966faade-b235-497d-96b3-81bbe057eae4" />
<br>
If you don't like soldering, you can also use a Waveshare ESP32-S3-RS485-CAN.<br>
In that case, you'll need to uncomment a line in the code.
<br>
<br>
<img width="693" height="604" alt="{2D58AFE9-AC4D-45B9-A595-55345EEAE659}" src="https://github.com/user-attachments/assets/c3556223-8993-448b-96bc-9af0b3821878" />
<br>
Connect the + and - terminals of the RS485 module using twisted-pair cable to the connector in the Tesla Wall Connector. If communication via RS485 isn't working, swap the connections.
<br>
<br>**Software**<br>
After turning on the ESP32, connect to the “Tesla Load Balancer” Wi-Fi network. You should be automatically redirected to the ESP's website. Select your own Wi-Fi network and enter the password.
<br>
<br>
You can enable load balancing on the WallConnector using the Tesla One app.
<br>
See also the detailed explanation at: https://github.com/Klangen82/tesla-wall-connector-control
