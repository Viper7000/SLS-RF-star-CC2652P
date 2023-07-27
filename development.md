# Board version 1.0 in development

## Schematic diagram of the board
![scheme](img/SCH.png)

## PCB layout
<img src="img/PCB1.png" style="height:400px;"> <img src="img/PCB2.png" style="height:400px;">

## Board appearance
<img src="img/2D1.png" style="height:400px;"> <img src="img/2D2.png" style="height:400px;">
<img src="img/3D1.png" style="height:400px;"> <img src="img/3D2.png" style="height:400px;">

## Boards received from the factory
![diagram](img/1.jpg)
![diagram](img/2.jpg)

## Assembled board and connector for installation in the gateway
<img src="img/3.jpg" style="height:450px;"> <img src="img/4.jpg" style="height:450px;">

To install, you need to shorten the light sensor tunnel. I have an Aqara M1S. Such modification is needed for some Xiaomi gateways. I also removed one small guide pin that was resting on the ESP32.
<img src="img/5.jpg" style="height:450px;">

## Settings
![scheme](img/set1.jpg) ![scheme](img/set2.jpg)

## Testing
For the initial test, the board was launched on the table. The firmware was installed via the USB connector by soldering jumpers on the board. After flashing the modules, the board started up and created an access point. I register the WiFi settings and save. The first time the board started up for a very long time. Zigbee status is 0. Not working. Although there is active communication with the Zigbee module in the logs. Additionally, I erased the PDM of the Zigbee module (although I did the erasure during firmware). I also changed the channel and PanID (standard pan on another gateway). Restart - everything works.

Checking the operation of Zigbee CC2652P - devices connect and respond. One of the devices in the back room. On 2538+2592 the signal to it was 10-20 LQI, on the module 2652 the signal was 80-90 LQI. Excellent result

The LED works, the effects work.

I soldered the jumpers on the board for connecting via USB to the ESP32. So you can see the logs on the computer

The LEDs connected to the Zigbee module (green and red) work depending on the firmware of the Zigbee module. On the latest Koenkk firmware CC1352P2_CC2652P_launchpad_coordinator_20230507.hex only red works. Other firmware did not check.
