---
title: Component Selection
---

## This page will discuss the details of the components that my system uses.

## Actuator

An actuator will be used to add more visual drama to our exhibit. When an audience member gains a point, the actuator will extend, and when an audience member loses the point, the actuator will retract. When the actuator hits a pushbutton (also assigned to my subsystem) the audience member has won the game and the actuator will retract to its original position. Here are a few possible solutions

| Solution                                      | Pros                                                        | Cons                                                                   |
| --------------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------------- |
| Solution 1 [Micro Linear Actuator](https://www.progressiveautomations.com/products/micro-linear-actuator?_pos=2&_fid=1a032d801&_ss=c) ![PA-07-5](https://github.com/user-attachments/assets/11a96e25-3cc1-4ccd-9e4e-5b7cbe82352e)                                  | Increased length,                                         | More expensive, less dynamic force, less speed                                                                       |
| Solution 2 [IP65 Micro Linear Actuator](https://www.progressiveautomations.com/products/pa-mc1?_pos=1&_fid=1a032d801&_ss=c) ![PA-MC1_main2](https://github.com/user-attachments/assets/de38046c-76fd-42ea-a370-c1d71d842808)                                  | Cheaper, faster speed, greater force                                                             | Less length (4 inches shorter than other solution)                                                                        |

Chosen Solution: [IP65 Micro Linear Actuator](https://www.progressiveautomations.com/products/pa-mc1?_pos=1&_fid=1a032d801&_ss=c)

Rationale: This is by far the cheapest and most efficient actuator for our project. Since the actuator does not require substantial force or reach, as it is part of a simple game mechanic, this cheap actuator can fit all the necessary purposes while fitting within the budget.

## Power Supply (Wall Mount)

| Solution                                      | Pros                                                        | Cons                                                                   |
| --------------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------------- |
| Solution 1 [VEL12US120-US-JA](https://www.digikey.com/en/products/detail/xp-power/VEL12US120-US-JA/5726833) ![MFG_VEL12-US_dist](https://github.com/user-attachments/assets/66bcf602-d8a4-41f8-b548-d566fcb2cf47)| Increased length, more power, sufficient aperage, greater efficiency  | More expensive|
| Solution 2 [L6R06H-120](https://www.digikey.com/en/products/detail/tri-mag-llc/L6R06H-120/7682617?gQT=1) ![Tri-Mag,L6R06H_Barrel-Plug](https://github.com/user-attachments/assets/611d6f9d-4754-4d69-82dc-c9f6d3ae8ddd) | Cheaper                                                          | Less amperage, less heat tolerance, less power        |
                                  
Chosen Solution: [VEL12US120-US-JA](https://www.digikey.com/en/products/detail/xp-power/VEL12US120-US-JA/5726833)

Rationale: Although not cheaper than the other option, it outweighs the other power supply in almost all stats in terms of performance. The amperage will be high for the microcontroller but can be easily regulated.

## Voltage Regulator

## Microcontroller

The model used in my subsystem will be the [ESP32-S3-WROOM-1_N4](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639). This is the surface mount version of the microcontroller used in our labs.

| ESP Info                                      | Answer                   | Help                                                                                                      |
| --------------------------------------------- | ------------------------ | --------------------------------------------------------------------------------------------------------- |
| Model                                         | ESP32-S3-WROOM-1 N4      | Include the entire part number (leave off any letters at the end that specify the package type)           |
| Product Page URL                              | [Product URL](https://www.espressif.com/en/producttype/esp32-wroom-32) | Found on Espressif.com                                                                                    |
| ESP32-S3-WROOM-1-N4 Datasheet URL             | [WROOM Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf)      | Do not paste links directly into the table.  Use a [link](#)                                              |
| ESP32 S3 Datasheet URL                        | [ESP32 Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3_datasheet_en.pdf)      | Has more detail on functions                                                                              |
| ESP32 S3 Technical Reference Manual URL       | [Technical Reference Manual](https://www.espressif.com/sites/default/files/documentation/esp32-s3_technical_reference_manual_en.pdf)      | Has details on I/O multiplexing, USB, and others                                                          |
| Vendor link                                   | [Digikey](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639)      | Digikey, Jameco, etc.  Do not paste links directly into the table.  Use a [link](#)                       |
| Code Examples                                 | [Simple Wifi Server](https://github.com/espressif/arduino-esp32/blob/master/libraries/WiFi/examples/SimpleWiFiServer/SimpleWiFiServer.ino)      | url(s) for libraries on github or other sites related to the microcontroller and your planned peripherals |
| External Resources URL(s)                     | [Introduction Video](https://youtu.be/xPlN_Tk3VLQ)      | Search on Google and YouTube for other resources for each specific microcontroller.                       |
| Unit cost                                     | $2.95      | Find on Digikey, Jameco, MPJA, or octopart                                                                |
| Absolute Maximum Current for entire IC        | 355mA      | Find in the microcontroller datasheet                                                                     |
| Supply Voltage Range                          | 3V~3.6V      | Min / Nominal / Max / Absolute Max, as found in datasheet                                                 |
| Maximum GPIO current <br> (per pin)           | 97mA      | as found in datasheet                                                                                     |
| Supports External Interrupts?                 | Yes      | as found in datasheet                                                                                     |
| Required Programming Hardware, Cost, URL      | [VSCode](https://code.visualstudio.com/) Free      | as found in datasheet                                                                                     |

| Module         | # Available | Needed | Associated Pins (or * for any) |
| -------------- | ----------- | ------ | ------------------------------ |
| UART           | 2           | 2      | TXD0, RXD0                     |
| I2C            | 2           | 0      | *                              |
| GPIO           | 33          | 2      | *                              |
| ADC            | 33          | 0      | *                              |
| LED PWM        | 33          | 0      | *                              |
| SPI            | 33          | 4      | *                              |
| USB Programmer | 2           | 2      | IO19-20                        |

\* The ESP32-S2 has multiple SPI interfaces, but some are for internal use

I have decided to go with the ESP32 WROOM as it is a surface mount microcontroller that provides all the necessary ports for my project, as it includes various PWM, SPI, UART, and GPIO pins, and transfers information at a high speed, making it ideal to use when communicating with the other subsystems my team has.

![AR3260-ESP32-S3-WROOM-1-N16R8-16MB-FLASH-8MB-PSRAM-Pinout](https://github.com/user-attachments/assets/05aadfef-9e8a-4a68-974e-4e48876619f8)

The EN and 3v3 will be connected, the GND pins will go to the necessary grounds, and the various GPIO pins will encompass PWMs, ADCs, UARTs, and SPIs and will be defined as their respective inputs/outputs.

## My Goal

This subsystem uses actuation in order to enhance a game mechanic as well as send information back to the other subsystems once the actuator hits the pushbutton and the game is complete. This will reset the programming of the rest of the subsystems so the game is refreshed and ready to be played by the next audience member.

