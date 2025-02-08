---
title: Component Selection
---

## This page will discuss the details of the components that my system uses.

## Actuator

An actuator will be used to add more visual drama to our exhibit. When an audience member gains a point, the actuator will extend, and when an audience member loses the point, the actuator will retract. When the actuator hits a pushbutton (also assigned to my subsystem) the audience member has won the game and the actuator will retract to its original position. Here are a few possible solutions

| ESP Info                                      | Pros                                                        | Cons                                                                   |
| --------------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------------- |
| Solution 1 [Micro Linear Actuator](https://www.progressiveautomations.com/products/micro-linear-actuator?_pos=2&_fid=1a032d801&_ss=c)                                   | Increased length,                                         | More expensive, less dynamic force, less speed                                                                       |
| Solution 2 [IP65 Micro Linear Actuator](https://www.progressiveautomations.com/products/pa-mc1?_pos=1&_fid=1a032d801&_ss=c)                                   | Cheaper, faster speed, greater force                                                             | Less length (4 inches shorter than other solution)                                                                        |


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
| UART           | 3           | 0      | ?                              |
| external SPI\* | 2           | 1      | ?                              |
| I2C            | 2           | 0      | ?                              |
| GPIO           | 36          | 1      | ?                              |
| ADC            | 20          | 2      | ?                              |
| LED PWM        | 36          | 0      | ?                              |
| Motor PWM      | 36          | 2      | ?                              |
| USB Programmer | 1           | 1      | ?                              |



\* The ESP32-S2 has multiple SPI interfaces, but some are for internal use
