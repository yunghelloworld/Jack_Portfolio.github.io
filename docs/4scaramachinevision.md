---
title: Machine Vision SCARA
---

This is a class project where I was assigned to create a manipulator that would pick up an object and place it into a bin. From servo motors, I built a SCARA manipulator with an electromagnet that would pick up a nut and put it in a bin. The placement of the nut was recorded by a USB camera hovering above the area where the SCARA would reach, and it would convert pixels of the camera recording to physical units in order to find the placement of the nut. A matlab script used inverse kinematics to compute the servo angles which would then be sent to the PSoC microcontroller via UART in order to change the position of the servos, as well as drive the electromagnet to pick up and drop off the nut into an offscreen bin.

# Diagram
<img width="612" height="385" alt="Diagram2" src="https://github.com/user-attachments/assets/88442ad2-0519-4555-88da-10023de1d798" />
