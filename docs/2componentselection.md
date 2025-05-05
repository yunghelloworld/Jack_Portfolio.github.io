---
title: Component Selection/Power Budget
---

## Actuator

An actuator will be used to add more visual interest to our exhibit. When an audience member gains a point, the actuator will extend, and when an audience member loses the point, the actuator will retract. When the actuator hits a pushbutton (also assigned to my subsystem) it will send a message to the display confirming that the audience member has won the game and the actuator will retract to its original position. Here are a few possible solutions.

| Solution                                      | Pros                                                        | Cons                                                                   |
| --------------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------------- |
| Solution 1 [Micro Linear Actuator](https://www.progressiveautomations.com/products/micro-linear-actuator?_pos=2&_fid=1a032d801&_ss=c) ![PA-07-5](https://github.com/user-attachments/assets/11a96e25-3cc1-4ccd-9e4e-5b7cbe82352e)                                  | Increased length,                                         | More expensive, less dynamic force, less speed                                                                       |
| Solution 2 [IP65 Micro Linear Actuator](https://www.progressiveautomations.com/products/pa-mc1?_pos=1&_fid=1a032d801&_ss=c) ![PA-MC1_main2](https://github.com/user-attachments/assets/de38046c-76fd-42ea-a370-c1d71d842808)                                  | Cheaper, faster speed, greater force                                                             | Less length (4 inches shorter than other solution)                                                                        |

Chosen Solution: [IP65 Micro Linear Actuator](https://www.progressiveautomations.com/products/pa-mc1?_pos=1&_fid=1a032d801&_ss=c)

Rationale: This is by far the cheapest and most efficient actuator for our project. Since the actuator does not require substantial force or reach, as it is part of a simple game mechanic, this cheap actuator can fit all the necessary purposes while fitting within the budget.

## Motor Driver

| Solution                                      | Pros                                                        | Cons                                                                   |
| --------------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------------- |
| Solution 1 [IFX9201SG](https://www.digikey.com/en/products/detail/infineon-technologies/IFX9201SGAUMA1/5415542?s=N4IgTCBcDaIJIDEAaBOMAGAjAZQOIEEBVAWX0xAF0BfIA) ![P-PG-DSO-12](https://github.com/user-attachments/assets/b3b52847-73ef-4240-a025-97c41bb56031) | Familiarity with technology, just enough pins, affordable  | Needs a 5V power source in order to function fully|
| Solution 2 [L2293QTR](https://www.digikey.com/en/products/detail/stmicroelectronics/L2293QTR/1992180) ![497_32-QFN Pkg](https://github.com/user-attachments/assets/07787b88-f1be-4acb-9b05-df7d1024afb6) | Lower supply threshold                                                          | More pins than necessary, difficult to solder       |
| Solution 3 [NCV7703CD2R2G](https://www.digikey.com/en/products/detail/onsemi/NCV7703CD2R2G/7325621) ![488~751A-03~D,-R,-W~14](https://github.com/user-attachments/assets/27986868-e51b-4cf6-9a00-ea5ca3e46354) | Lower enough supply threshold to support 3.3V with a decent load range             | Less detailed datasheet compared to other solutions, less familiar technology   

Chosen Solution: [NCV7703CD2R2G](https://www.digikey.com/en/products/detail/onsemi/NCV7703CD2R2G/7325621)

Rationale: It has the simple pin layout of the IFX9201SG along with the ability to use 3.3V supply for logic exclusively, making it the best out of the other options for this project.

## Voltage Regulator

| Solution                                      | Pros                                                        | Cons                                                                   |
| --------------------------------------------- | ----------------------------------------------------------- | ---------------------------------------------------------------------- |
| Solution 1 [MIC29302WU](https://www.digikey.com/en/products/detail/microchip-technology/MIC29302WU-TR/771594) ![576-TO-263-5](https://github.com/user-attachments/assets/e86b50a8-b0ed-4a03-b34a-83cfe15ff275)| Surface mount, increased amperage if necessary, higher voltage output, shorter manufacturer time, cheaper | Lower voltage input, less familiar with technology |
| Solution 2 [LM2575T](https://www.digikey.com/en/products/detail/onsemi/LM2575T-ADJG/918471) ![296~4040208~KC~5](https://github.com/user-attachments/assets/926bc5b7-204d-465a-ac84-0c97c5abb647)| Familiar with technology, larger range of voltage outputs                                                        | More expensive, through hole        |
| Solution 3 [LM2575D2T](https://www.digikey.com/en/products/detail/onsemi/LM2575D2T-3-3G/1476686) ![488~936A-02~DS,D2T~5](https://github.com/user-attachments/assets/5b067c1c-41a9-4358-913f-ba007e9f3530)| Similar stats as above solution but surface mount, cheaper                                                         | Fixed output        |

Chosen Solution: [LM2575D2T](https://www.digikey.com/en/products/detail/onsemi/LM2575D2T-3-3G/1476686)

Rationale: It has the LM2575 technology I am more familiar with as well as being surface mount, which is a requirement for this project. Although the output is fixed at 3.3V, this does not inhibit my system at all as 3.3V is enough to supply the logic of both my microcontroller and my motor driver.

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

The 3.3 will receive 3.3V, and 3.3V will be supplied to EN and BOOT with a pushbutton that can pull them to GND if necessary. The GND pins will go to the necessary grounds, and the various GPIO pins will encompass the SPI and generic inputs and outputs. RX and TX will be connected to the 8 pin daisy chain in order to foster communication.

## Summary of Selected Components

| Component Type     | Part Description              | Manufacturer             | Part Number        | Link                                                                                  |
| ------------------ | ----------------------------- | ------------------------ | ------------------ | ------------------------------------------------------------------------------------- |
| **Actuator**       | IP65 Micro Linear Actuator    | Progressive Automations  | PA-MC1             | [Product Page](https://www.progressiveautomations.com/products/pa-mc1?_pos=1&_fid=1a032d801&_ss=c) |
| **Motor Driver**   | DC Motor Driver               | ON Semiconductor         | NCV7703CD2R2G      | [Digikey](https://www.digikey.com/en/products/detail/onsemi/NCV7703CD2R2G/7325621)    |
| **Voltage Regulator** | 3.3 V Voltage Regulator    | ON Semiconductor         | LM2575D2T-3.3G     | [Digikey](https://www.digikey.com/en/products/detail/onsemi/LM2575D2T-3-3G/1476686)    |
| **Microcontroller** | ESP32-S3-WROOM-1 N4 Module   | Espressif Systems        | ESP32-S3-WROOM-1_N4 | [Espressif](https://www.espressif.com/en/producttype/esp32-wroom-32)                   |

## Decision Making

When selecting components, I first checked if the specs of each meshed with what I was planning orignally. I made sure none of the components could draw too much current and that voltage requirements were all kept within a range that allowed for 12V and 3.3V. The actuator was reused from a previous class, and already showed the level of functionality necessary for completing this project. The motor driver was different from the one used in class, as it was more convenient to use the 3.3V logic instead of the 5V logic as there would be less power rails. The ESP32 was chosen for its versatility and ability to be coded in micropython, which was much more familiar me than MPLab, which was necessary if I were to program the PIC.

# Power Budget 

![powerbudget](https://github.com/user-attachments/assets/e3d98c07-2ef0-4be6-97be-7b654522dd6d)

[Power Budget.pdf](https://github.com/user-attachments/files/20018791/Untitled.spreadsheet.-.Power.Budget_removed.pdf)

## Decision Making

The power budget gave me further awareness of how power is distributed throughout me and my team's subsystems. I had to choose a power supply that had a lot more current than my old one, as the max current from each of my components would exceed the max current the power supply could provide. The microcontroller also has a limited amount it can draw, so components directly connected to the microcontroller needed to be curated so that the chip would not be fried from excessive current. A 20% margin for error was included in case of current spikes within the system.
