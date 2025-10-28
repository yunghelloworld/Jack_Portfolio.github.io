---
title: Homing Camera
tags:
- tag1
- tag2
---

# Diagram
<img width="597" height="496" alt="Diagram" src="https://github.com/user-attachments/assets/bd6117a0-6dd7-4a1c-ab41-f1e12e932fa7" />

This was a class project in which I was assigned to create a system that was able to track and follow objects. I put together simple hardware such as a DC stepper motor, a basic USB camera, and used a fastener in order to screw the camera into the fastener so it could be controlled by the motor's peg. The camera's graphical information was interpreted by a python script that would communicate the distance of a red object from the middle of the screen. It detected red objects by determining where a significant amount of red particles were detected together and tracked it as an object. This made it so individual red particles were ignored. I also used a library that would turn the particles into a larger mesh so that there wasn't noise within the camera's recording of the red object that would stop it from detecting. After this it would use a PID algorithm to compute the velocities necessary in order to reach the red object without jittering or oscillation. This python script then communicated those velocity values to PSoC via UART in order to change the velocity of the stepper motor as the red object gets either further or closer from the middle of the camera lens. When no red object is detected, the camera enters patrol mode where it moves its lens back and forth until a red object is detected.
