# Pi3-videostream
Stream video from Raspberry Pi3 Generic Camera to VMS Media Server

Run NxWitness MediaServer on Raspberry Pi 3 and stream video to it from Raspberry Pi Generic Camera.
====================================================================================================


Requirements:
-------------


- __Nx Version__: 3.2


- __Raspbian Stretch from__: April 2018


- __RPI__: Raspberry Pi Camera Module V2 and up


- __VLC__ media palyer


Links:
------


https://www.raspberrypi.org/downloads/raspbian/


https://github.com/binnes/tobyjnr/wiki/Raspberry-Pi-Initial-setup


https://support.networkoptix.com/hc/en-us/articles/217453737-Raspberry-Banana-Pi-Installation-Guide


https://beta.networkoptix.com/beta-builds/default/20198/arm/nxwitness-server-3.2.0.20198-rpi-beta-prod.zip


General Diagram:
-----------------
![Screenshot](https://github.com/kolobokzaebok/Pi3-videostream/blob/master/images/dm.jpg)



Step 1. Create an RTSP stream
-----------------------------


Once you have your Raspberry Pi configured and running, open a terminal window or via SSH type in the command below and hit "Enter":


raspivid -o - -t 0 -n -w 1280 -h 720 -fps 15 | cvlc -A alsa, none —alsa-audio-device default -vvv stream:///dev/stfin — sout ‘#rtp{sdp=rtsp://:5001/x}’ :demux=h264


The command will create an RTSP stream as shown below:


__rtsp://127.0.0.1:5001/x__


Step 2. Add device to your media server
----------------------------------------


- Open NxWitness Client on your computer and connect to the MediaServer running on your Pi.


- Right click on the Server and choose "Add Device" from a drop-down menu.


- Insert the link and click "Scan".


- Once done, click "Add selected".


- The Camera will appear on the List of Devices and will be ready for use.
































