# CHAIRNESS OF A CHAIR
## Hochschule Augsburg - Interactive Media - 5th Semester - Wicked Things

This repository contains source of codes and informations about the hardwares and its hacking. Everything that is needed to hack a hoverboard and control it with Arduino and Processing to make a fully functional remote controlled moving chair can be found here. Some codes and methods are taken from other GitHub Repositories as well, the link will be provided in in the description.

## TABLE OF CONTENT
- [HARDWARE](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#hardware)
- [FLASHING](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#flashing)
- [ARDUINO](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#arduino)
- [PROCESSING](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#processing)
- [CONTROLLER](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#controller)
- [TRACKING](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#tracking)
- [PROTOTYPE](https://github.com/janenathania/chairness-of-a-chair/blob/main/README.md#prototypes)

## HARDWARE

For this project we use the older version of the hoverboard that only has one chip to control both side of the hoverboard.
The main model of the chip is STM32F103. 

<img src="https://user-images.githubusercontent.com/77440248/151607800-edf9a9e2-9648-49fb-9b58-bb1d83cd3ad4.png" width="350"/> <img src="https://user-images.githubusercontent.com/77440248/151600772-356a5a8d-d064-4ff4-ac20-b5cc60d0df6a.png" width="350"/>

Further information and instruction can be found in a GitHub Repository by lucysrausch
https://github.com/lucysrausch/hoverboard-firmware-hack

## FLASHING

In order to control the hoverboard we have to hack the firmware first. Fristly we have to erase every progamms that are built in the hoverboard.
The method is called flashing. There are several methods to do the flashing

Further description about flashing can be read here
https://github.com/lucysrausch/hoverboard-firmware-hack#flashing

And the various method of flashing can be found in the GitHub Repository by EFeru
https://github.com/EFeru/hoverboard-sideboard-hack-STM#flashing

## ARDUINO

(TODO) General Explanation of the code, the connection between hoverboard, programm, processing and controller's input

GitHub Repository from HybridThingsLab
https://github.com/HybridThingsLab/wicked-things-2021/tree/main/01_playground/Arduino

## PROCESSING

(TODO) General Explanation of the code, the connection between hoverboard, programm, arduino and controller's input

GitHub Repository from HybridThingsLab
https://github.com/HybridThingsLab/wicked-things-2021/tree/main/01_playground/Processing

## CONTROLLER

(TODO) Code for the controller (input and output, sending and receiving)

<img src="https://user-images.githubusercontent.com/77440248/151609993-f13bb5a5-c5b9-49c2-88a9-efb06408dc7e.jpg" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151610040-703d8e17-dfa0-4916-9c87-662558387574.jpg" width="300"/>

The controller are made main from an arudino joystick kit and it is covered with a 3D printed cover. To make it a cleaner look and more rigid body. It makes the controller easier to hold it and comfortable while using it, so that the controllers can controll the chair precisely.

## TRACKING

(OPTIONAL)

## PROTOTYPES

To ensure that the chair is safe to ride we have done some experiments on the shape of the chair and the supporting board the is built between the hoverboard and the actual chair.

<img src="https://user-images.githubusercontent.com/77440248/151605415-947c6714-a6aa-4f4c-865b-f437abc0128f.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151605916-191323c4-486c-4156-b1c5-5e11a9ca946d.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151607956-cd2b1faf-1ef6-4138-8c52-8d5750fae49e.jpg" width="300"/>

The board acts not only as a support that connect hoverboard and the chair, but also as a place to put the motherboard that control the whole thing.

<img src="https://user-images.githubusercontent.com/77440248/151608508-0ca63d9b-1e95-4ca1-adb6-35e174e6f20e.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151608591-879c75f1-8ebe-472b-8860-7dc619d72607.png" width="300"/> <img src="https://user-images.githubusercontent.com/77440248/151608778-fb026589-fa99-44a2-a673-da10f999b1d8.png" width="150"/>

The final design of the chair. The shape of the chair is chosen after several user tests to decide which shape is the safest to ride on. The important feature of the moving chair is its backrest. It is to protect the user from falling over during sudden movement of the chair.
The board at the bottom is made quite broad. It is made like that to make sure that the user has enough space to place their feet on it and feel sturdy while sitting on the chair. The board itself has in total 5 wheels. 2 wheels are from the hoverboard that can move following the controllers input and the other 3 wheels are the supporting wheels (2 in front and 1 at the back) to make sure that the whole chair doesn't flip over during sudden movement or sudden break.

### Notes
Interaktive Medien - 5. Semester - Wicked Things

- Table of Content
  - Board Types (Chips)
  - Flashing -> EFeru Tutorial
  - Arduino + Processing -> GitHub von HybridThingsLab
  - Controller (Code + Design)
  - (Tracking: Extra)
  - Prototypes -> aktueller

- Bilder, Formulieren
