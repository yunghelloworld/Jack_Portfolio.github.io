---
title: Block Diagram
---

![Block Diagram-314 drawio (4)](https://github.com/user-attachments/assets/3eb322b1-67b7-4457-8c31-dd96aef73d0f)
Updated 5/2/25

My updated block diagram showcasing the simplified individual components my subsystem uses, including a switching voltage regulator, wall mounted power supply, a microcontroller, a motor driver, and an actuator. The actuator will be activated when my microcontroller receives data from another subsystem which will tell the actuator when to go to a actuating or retracting state. There are multiple digital pins for SPI communication, USB , and a singular digital pin that will act as a victory button for when the actuator presses it. A unregulated 12V voltage will be used to power the motor, but regulated 3.3V will power the logic of the motor driver and the micro controller.

I developed this diagram to show all bits of relevant information of how my system worked if someone were to take a quick glance. Included all relevant components to the actual functionality of my subsystem which will be demonstrated within my project. Updates were made to show new components and connection nuances that were once missing, as well as proper pin names.
