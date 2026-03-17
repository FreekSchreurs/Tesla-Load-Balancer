Based on info from https://github.com/dracoventions/TWCManager/issues/20 I made, with the help of the AI Claude, an ESPHome yaml to search my network for a HomeWizard p1 meter and use that data to emulate a Neurio Energy Meter, thereby adding load balancing to my Tesla Wall Connector 3.
Claude's work still needed a lot of attention. In the end, it took me about 25 iterations before I manually resolved the rest.

**Hardware**
For this I used the following hardware:<br>
<img width="300" alt="image" src="https://github.com/user-attachments/assets/68d806b3-4f4a-4804-b5fa-48a494ebd68a" />
<br>
esp32-s3-devkitc-1 n16r8: https://nl.aliexpress.com/item/1005010579778226.html and
<br>
<img width="220" height="220" alt="image" src="https://github.com/user-attachments/assets/eb518170-e133-4786-9455-f3e5809007e1" />
<br>
RS485 to serieel module: https://nl.aliexpress.com/item/1005010275911984.html 
but knowing what I know now, I would have ordered
<br>
<br>
<img width="300" alt="image" src="https://github.com/user-attachments/assets/2af65309-9071-4cb7-bd34-48290970d315" />
<br> this module: https://nl.aliexpress.com/item/1005008635626105.html
<br>
<br>
This is what it looks like after the parts have been soldered together:
<br>
<img width="800" alt="image" src="https://github.com/user-attachments/assets/40cbb17e-ede2-4997-9d56-58a35fb233bd" />
<br>
If you don't like soldering, you can also use a Waveshare ESP32-S3-RS485-CAN.
In that case, you'll need to uncomment a line in the code.
<br>
<br>
<img width="600" alt="image" src="https://github.com/user-attachments/assets/df6e74cf-6b80-4c3c-a16e-e753318e7472" /><br>

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
