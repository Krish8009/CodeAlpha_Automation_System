<p align="center">
  <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Presence.png"/>
</p>
<h1 align="center">Presence Package</h1>
<p align="center">Be sure to :star: my repo!</p>
<hr *** </hr>
<p align="center">This package incorporates the device trackers I use to detect our home or away presence and use these to fire off Automations and TTS messages. In order to improve my home state accuracy I use BLE trackers for detecting home status which is working very very well, whilst I'm out and about I use owntracks with tasker on my android phone to force updates whenever I connect/disconnect from wifi/bluetooth/airplane mode. I not only monitor my wife and I presence I also monitor my bins presence to further automate my trash collection routines aswell as montioring our cars with BLE Tile devices.</p>
<hr --- </hr> 

<h4 align="left">Package Credits:</h4>

[Monitor](https://github.com/andrewjfreyer/monitor#an-example-use-with-home-assistant)

[HA Forum](https://community.home-assistant.io/t/reliable-multi-user-distributed-bluetooth-occupancy-presence-detection/50674/285)

[Brad](https://diyfuturism.com/index.php/2017/11/26/presence-detection-with-home-assistant-bayesian-probability/)

<hr --- </hr>

<h4 align="left">Package Dependencies:</h4>
<p align="left">- MQTT Broker</br>
<h4 align="left">Package Device Trackers:</h4>
<h4 align="left">Ping</h4>
<p align="left">This tracker uses the ping component as a metric for calculating if I have just arrived home or just left home, it isn't good for much then that as our phones go to sleep and turn Wi-Fi off when they do. It works quiet well to establish just got home/just left however.</br>
<h4 align="left">GPS Logger</h4>
<p align="left">This tracker uses GPS location from our phones to update HA as to where we are this component works perfectly especially when moving over from owntracks which just doesn't work reliably enough. I have managed to improve this with tasker on my android firing whenever I connect/disconnect from Wi-FI/Bluetooth or select Airplane mode.</br>
<h4 align="left">Bluetooth Detection</h4>
<p align="left">This tracker uses HASSIO with Bluetooth addon and Bluetooth tracker component configured. This tracks our phones and works pretty well.</br>
<h4 align="left">BLE Tag Detection</h4>
<p align="left">This tracker uses the Monitor script running on a pi zero and tracks if our bluetooth beacons are in the home zone or not.</br>
<h4 align="left">Bayesian Sensor</h4>
<p align="left">This brings the best of all the methods above together to detect the probability that I am indeed home or away. I assume if I can ping my device I'm home, I also assume if more then one of my methods thinks I'm home then thats probably where I am. This is as close to perfect presence detection as I can acheive. I should mention that I also use Node-RED to combine my trackers to come up with the best probability that I'm home.</br>
<h4 align="left">Package Inputs:</h4>
<p align="left">There are 2 input booleans which are triggered by the BLE trackers located around the house, these are then used to update home/away status aswell as trigger automations.</p>
<h4 align="left">Package Sensors:</h4>
<p align="left">In this package I use the MQTT json.batt value to provide battery level for our phones, also use json.confidence value to use as part of the mean average sensor. I use the Rest sensor to get the api state from each BLE Tracker Pi these are used to update the state of the template sensor. I use this template sensor to be feed by all of my trackers with the latest known state and have found it reliable.</br>
<h4 align="left">Package Automations:</h4>
<h4 align="left">Trigger Occupancy after HA Restart</h4>
<p align="left">This automation sets the input_boolean to the current state after a restart as I do atleast 5 of those a day.</p>
<h4 align="left">James Occupancy Home</h4>
<p align="left">This automation uses the state of each of the ble trackers to update the input_boolean it will turn it on whenever any of them changes their state to home..</p>
<h4 align="left">James Occupancy Away</h4>
<p align="left">This automation uses the state of a group containing all of the ble trackers if they are all 'away' then it triggers the input_boolean to turn of which will change the state of the sensor.james in the UI.</p>
<h4 align="left">James Home/Away</h4>
<p align="left">This automation updates the template sensor of my state I find there is normally a 3 minute delay between ble tracker and the owntracks app being the owntracks is always quicker as tasker tells it to update as soon as I get out of the car as it disconnects from the bluetooth.</p>
<h4 align="left">James/Tina Home Announcement</h4>
<p align="left">This automation plays a specific TTS message notifying everyone that we have arrived, as with any of my TTS stuff it really is to mess with my wife as she hates them.</p>
<h4 align="left">James Work Travel Announcement</h4>
<p align="left">These automations plays specfic TTS announcements to let my family know I have arrived safely at work, I've just left work with est travel time, I'm 25/15/5 mins from home.</p>
<h4 align="left">James at Shops</h4>
<p align="left">This automation plays a TTS message to let my wife know I'm at the shops and to send me a list of anything else we might need. I will be updating this with another project that puts a Pi with camera in the fridge using machinebox to create a shopping list based on the status of the fridge contents.</p>
<hr --- </hr>

| Automations! | [Node-RED-Flow](https://github.com/JamesMcCarthy79/Home-Assistant-Config/tree/master/config/packages/presence/Node-RED%20Flow) | [YAML](https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/config/packages/presence/presence.yaml) |
| --- | --- | --- |

| Take me back to the packages thanks!| [Packages](https://github.com/JamesMcCarthy79/Home-Assistant-Config/tree/master/config/packages) | 
| --- | --- |

<hr --- </hr>
