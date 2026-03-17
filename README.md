Based on info from https://github.com/dracoventions/TWCManager/issues/20 I made, with the help of the AI Claude, an ESPHome yaml to search my network for a HomeWizard p1 meter and use that data to emulate a Neurio Energy Meter, thereby adding load balancing to my Tesla Wall Connector 3.
Claude's work still needed a lot of attention. In the end, it took me about 25 iterations before I manually resolved the rest.

**Hardware**
For this I used the following hardware:<br>
<img width="480" height="240" alt="{9107FE65-E2D5-4174-AE9B-F978A917C16E}" src="https://github.com/user-attachments/assets/78b1314c-f4e0-42f7-877b-2e34ff23b726" />
<br>
esp32-s3-devkitc-1 n16r8: https://nl.aliexpress.com/item/1005010579778226.html and
<br>
<img width="519" height="410" alt="{9B683857-5FE6-4D31-86F9-13EAB3377254}" src="https://github.com/user-attachments/assets/ab034022-030b-43f1-b84c-b84da177bc3f" />
<br>
RS485 to serieel module: https://nl.aliexpress.com/item/1005010275911984.html 
but knowing what I know now, I would have ordered
<br>
<br>
<img width="466" height="336" alt="{C95F06F8-0D7F-46F4-A6FD-95BD7A950317}" src="https://github.com/user-attachments/assets/3328a0d6-b0c9-42fd-b15c-04bf20ebdb39" />
<br> this module: https://nl.aliexpress.com/item/1005008635626105.html
<br>
<br>
This is what it looks like after the parts have been soldered together:
<br>
<img width="1421" height="325" alt="{E771A27B-CB0E-4071-BEE7-58BBA7FE2A7C}" src="https://github.com/user-attachments/assets/966faade-b235-497d-96b3-81bbe057eae4" />
<br>
If you don't like soldering, you can also use a Waveshare ESP32-S3-RS485-CAN.
In that case, you'll need to uncomment a line in the code.
<br>
<br>
<img width="693" height="604" alt="{2D58AFE9-AC4D-45B9-A595-55345EEAE659}" src="https://github.com/user-attachments/assets/c3556223-8993-448b-96bc-9af0b3821878" />
<br>
Connect the + and - terminals of the RS485 module using twisted-pair cable to the connector in the Tesla Wall Connector. If communication via RS485 isn't working, swap the connections.
<br>
<br>
**Software**
<br>
After turning on the ESP32, connect to the “Tesla Load Balancer” Wi-Fi network. You should be automatically redirected to the ESP's website. Select your own Wi-Fi network and enter the password.
<br>
<br>
You can enable load balancing on the WallConnector using the Tesla One app.
<br>
See also the detailed explanation at: https://github.com/Klangen82/tesla-wall-connector-control
