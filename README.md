# CHAIRNESS OF A CHAIR
## Hochschule Augsburg - Interactive Media - 5th Semester - Wicked Things

This repository contains source of codes and informations about the hardwares and its hacking. Everything that is needed to hack a hoverboard and control it with Arduino and Processing to make a fully functional remote controlled moving chair can be found here. Some codes and methods are taken from other GitHub Repositories as well, the link will be provided in in the description.

## TABLE OF CONTENT
- [HARDWARE](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#hardware)
- [FLASHING](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#flashing)
- [SERIAL INTERFACE](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#serial_interface)
- [ARDUINO](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#arduino)
- [PROCESSING](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#processing)
- [PROTOTYPE](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#prototypes)
- [3D PRINT](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#3d_print)

## HARDWARE

For this project we use the older version of the hoverboard that only has one chip to control both side of the hoverboard.
The main model of the chip is STM32F103. 

<img src="https://user-images.githubusercontent.com/77440248/151607800-edf9a9e2-9648-49fb-9b58-bb1d83cd3ad4.png" width="350"/> <img src="https://user-images.githubusercontent.com/77440248/151600772-356a5a8d-d064-4ff4-ac20-b5cc60d0df6a.png" width="350"/>

Further information and instruction can be found in a GitHub Repository by lucysrausch <br/>
https://github.com/lucysrausch/hoverboard-firmware-hack

## FLASHING

In order to control the hoverboard we have to hack the firmware first. Fristly we have to erase every progamms that are built in the hoverboard.
The method is called flashing. There are several methods to do the flashing

Further description about flashing can be read here <br/>
https://github.com/lucysrausch/hoverboard-firmware-hack#flashing

And the various method of flashing can be found in the GitHub Repository by EFeru <br/>
https://github.com/EFeru/hoverboard-sideboard-hack-STM#flashing

We also follow the instructions from this GitHub repository
The Method that we follow to make this project is `VARIANT_USART` <br/>
https://github.com/EFeru/hoverboard-firmware-hack-FOC

## SERIAL INTERFACE
### ESP Code

Parts used:
- Hoverboard with STM32F103 chip
- ESP8266
- DC/DC Converter
- Wireless Router (we use tp-link TL-MR3020)

If you are using a ESP for the first time, follow these instructions to get ready to use it: https://randomnerdtutorials.com/how-to-install-esp8266-board-arduino-ide/

Then import these two libraries to your Arduino IDE:
- Ramp for motors https://github.com/siteswapjuggler/RAMP
- Protocoll for wireless communication between Processing and ESP https://sojamo.de/libraries/oscP5/network

You need a Wireless Router with an AP Mode. In the Code you have to change the SSID and PWD into your own password for the router
If you are building two chairs like us, you might have to change the last digit of the IPAddress for the second ESP
Each Chair requires 1 ESP and the IPAdress should be different from each other

`const IPAddress ip(192, 168, 1, 202); change the 202 to 203.`

<img src="https://user-images.githubusercontent.com/77440248/151657172-a148da69-c341-4123-b19f-6487a0d3ba0e.png" width="500"/>

After that you can upload our ESP-Code to your ESP. 

### ESP Build

Disconnect the Sideboard which is on the side of the mainboard. Take your ESP and DC Converter and connect everything like this:
- 15V red wire goes to the left wire of the converter, which is labeled with `in`
- TX blue wire goes to the RX pin of the ESP
- RX green wire goes to the TX pin of the ESP
- GND black wire goes to the middle wire of the converter with the `ground` label
- connect another black wire to the middle wire of the converter and put it on the GND pin on the ESP
- the last wire of the converter (adjust 5V out) goes to the Vin pin of the ESP 

<img src="https://user-images.githubusercontent.com/77440248/151657231-8c02906d-379f-44cd-a9d5-13ed2c650a48.png" width="500"/>

Original Links of the images <br/>
- https://m.media-amazon.com/images/I/51Z9NoCxWwL._SL1000_.jpg
- https://wiki.volkszaehler.org/_media/hardware/controllers/amica-nodemcu-esp8266-lua-cp2102-wifi-development-module-iot-gujarat.png
- https://github.com/EFeru/hoverboard-firmware-hack-FOC/blob/master/docs/pictures/mainboard_pinout.png

## ARDUINO

Parts used:
- 1x Arduino Uno
- 1x Seedstudio Grove Shield
- 2x Seedstudio Grove Joystick

Our Code is able to steer two hoverboards at the same time.

We used an Arduino Uno with the Seedstudio Grove Shield on top and we connect the first Seedstudio Grove Joystick to the A0 and the second Joystick to the A2 Connector of the Grove Shield.

We send the coordinates of the Joysticks as a string over the serial port.

GitHub Repository from HybridThingsLab <br/>
https://github.com/HybridThingsLab/wicked-things-2021/tree/main/01_playground/Arduino

## PROCESSING

Processing is able to read the data from the Arduino and send it over WLAN to the ESP.

To make sure that everything is working correctly you need use Processing 4 as the software.

Open the processing code (that you can find in the folder above) and connect your arduino to your pc. Run the code and check if there is an error. If so that means the code uses the wrong usb port. Check the number of your port on which your arduino is connected to and change it in the code.

<img src="https://user-images.githubusercontent.com/77440248/151657297-9a5a3cc4-35cf-4680-81e3-b410ae3fe2b5.png" width="600"/>

If there are two squares and you can move them with the joysticks, then everything is working fine.

Now start the hoverboard and connect the Wlan of your PC with the Router and run the processing code .

If everything is correct, your hoverboard should move if you use the joysticks.

<img src="https://user-images.githubusercontent.com/77440248/151657319-057fbf59-370b-4331-8d10-83c9547a528a.png" width="250"/>

GitHub Repository from HybridThingsLab <br/>
https://github.com/HybridThingsLab/wicked-things-2021/tree/main/01_playground/Processing

## PROTOTYPES

To ensure that the chair is safe to ride we have done some experiments on the shape of the chair and the supporting board the is built between the hoverboard and the actual chair.

<img src="https://user-images.githubusercontent.com/77440248/151605415-947c6714-a6aa-4f4c-865b-f437abc0128f.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151605916-191323c4-486c-4156-b1c5-5e11a9ca946d.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151607956-cd2b1faf-1ef6-4138-8c52-8d5750fae49e.jpg" width="300"/>

The board acts not only as a support that connect hoverboard and the chair, but also as a place to put the motherboard that control the whole thing.

<img src="https://user-images.githubusercontent.com/77440248/151608508-0ca63d9b-1e95-4ca1-adb6-35e174e6f20e.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151608591-879c75f1-8ebe-472b-8860-7dc619d72607.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151608778-fb026589-fa99-44a2-a673-da10f999b1d8.png" width="150"/>

The final design of the chair. The shape of the chair is chosen after several user tests to decide which shape is the safest to ride on. The important feature of the moving chair is its backrest. It is to protect the user from falling over during sudden movement of the chair.
The board at the bottom is made quite broad. It is made like that to make sure that the user has enough space to place their feet on it and feel sturdy while sitting on the chair. The board itself has in total 5 wheels. 2 wheels are from the hoverboard that can move following the controllers input and the other 3 wheels are the supporting wheels (2 in front and 1 at the back) to make sure that the whole chair doesn't flip over during sudden movement or sudden break.

## 3D PRINT

This is our extra parts. We make the cover for controllers, Arduino and ESP with 3D Print. You can make it with anything you like. But we attached the raw files of the 3D Models so you can try to 3D Print it if you have a 3D Printer.

<img src="https://user-images.githubusercontent.com/77440248/151657341-2edd07da-48df-49e2-87d1-cc1b9053c958.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151657417-ebe13f8d-c7a7-48c3-b7b2-5f384e9db4d1.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151657423-f311951b-1c3f-41c3-bacf-bf268a4fae0a.png" width="300"/>

The controller are made main from an arudino joystick kit and it is covered with a 3D printed cover. To make it a cleaner look and more rigid body. It makes the controller easier to hold it and comfortable while using it, so that the controllers can controll the chair precisely. <br/>

<img src="https://user-images.githubusercontent.com/77440248/151609993-f13bb5a5-c5b9-49c2-88a9-efb06408dc7e.jpg" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151610040-703d8e17-dfa0-4916-9c87-662558387574.jpg" width="300"/>
