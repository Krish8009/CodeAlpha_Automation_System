<p align="center">
  <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Media.jpg" width="350"/>
</p>
<h1 align="center">Media Package</h1>
<p align="center">Be sure to :star: my repo!</p>
<hr *** </hr>
<p align="center">This package utilises states of my media players to automate lights during playback visitors etc.</p>
<hr --- </hr> 

<h4 align="left">Package Credits:</h4>
<p align="left">Me :bowtie:</br>

<hr --- </hr>

<h4 align="left">Package Dependencies:</h4>
<p align="left">- Media Players enabled in your configuration I use Kodi but it could work with Plex with minor changes</br>
<p align="left">- Optional Doorbell Intergration</br>
<p align="left">- Lights enabled in your configuration</br>
<p align="left">- Configured scenes for lighting (I use multiple lights in the scenes)</br>
<h4 align="left">Package Automations:</h4>
<h4 align="left">Door Bell Pressed</h4>
<p align="left">If the doorbell is pressed whilst we are watching Kodi/TV the system will pause what we are watching. It used to flash the lights and pop up a picture of who is at the door but due to recabling for this section where the camera is it will temporarily disabled.</p>
<h4 align="left">Door Bell Pressed Night</h4>
<p align="left">If the doorbell is pressed whilst we are watching Kodi/TV the system will pause what we are watching. It also brightens the lights that would have been dimmed due to watching TV at night.</p>
<h4 align="left">Dim Lights for Lounge Media</h4>
<p align="left">If after 7pm but before 4am and kodi changes state from 'idle' to 'playing' the lights in the lounge amd dining area are dimmed to around 15% by using a script to select lights and brightness.There is also an automation that dims the lights if the state changes from 'paused' to 'playing'</p>
<h4 align="left">Lights Normal after Media</h4>
<p align="left">If after 7pm but before 4am and kodi changes state from 'playing' to 'idle' the lights in the lounge amd dining area are turned up to around 75% by using a script to select lights and brightness. There is also an automation that brightens the lights if the state changes from 'playing' to 'paused'</p>
<hr --- </hr>

| Automations! | [Node-RED-Flow](https://github.com/JamesMcCarthy79/Home-Assistant-Config/tree/master/config/packages/media/Node-RED%20Flow) | [YAML](https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/config/packages/media/media.yaml) |
| --- | --- | --- |

| Take me back to the packages thanks!| [Packages](https://github.com/JamesMcCarthy79/Home-Assistant-Config/tree/master/config/packages) | 
| --- | --- |

<hr --- </hr>
