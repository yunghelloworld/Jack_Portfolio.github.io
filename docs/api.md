---
title: API
---

# API

This page documents the API for my actuator subsystem and details the messages going to and from it.

---

### Start/Stop 

| Start              | Stop |
|-------------------|---------|
| AZ                 | YB     |


### Team Addresses

| Name              | Address |
|-------------------|---------|
| Pressure Sensor   | L       |
| OLED Display      | S       |
| Actuator          | J       |
| Broadcast (All)   | X       |

---

## Messages Received

### Message Type 1: Set Target Pressure
*Description:*  
The pressure sensor (Luke) sends the target pressure value. When the target pressure is reached, the actuator will extend

| Byte(s) | Variable Name    | Variable Type | Min Value | Max Value | Example |
|---------|------------------|---------------|-----------|-----------|---------|
| 1-4     | target_pressure  | float         | 0.0       | 100.0     | 55.5    |

---

### Message Type 2: Pressure Input
  
The pressure sensor broadcasts the current pressure reading. This data is used by all subsystems; for the actuator, it determines when to extend or retract.

| Byte(s) | Variable Name     | Variable Type | Min Value | Max Value | Example |
|---------|-------------------|---------------|-----------|-----------|---------|
| 1-4     | current_pressure  | float         | 0.0       | 100.0     | 55.5    |

---

## Messages Sent/Broadcasted

### Message Type 3: Display Target Pressure
 
Upon receiving the target pressure, the actuator sends this value to the OLED display (Shane) so that it can be shown on screen to the player.

| Byte(s) | Variable Name    | Variable Type | Min Value | Max Value | Example |
|---------|------------------|---------------|-----------|-----------|---------|
| 1-4     | target_pressure  | float         | 0.0       | 100.0     | 55.5   |

---

### Message Type 4: Actuator Control

This command tells the actuator to either extend or retract. The actuator extends when the pressure input equals the target pressure and retracts if the target is missed within time limit.

| Byte(s) | Variable Name | Variable Type | Min Value | Max Value | Example |
|---------|---------------|---------------|-----------|-----------|---------|
| 1       | actuator_state| uint8_t       | 0         | 1         | 1       |

---

### Message Type 5: Stop Game and Reset
  
When the pushbutton connected to the microcontroller is pressed, this message is broadcast to all subsystems to stop the game and reset the system.

| Byte(s) | Variable Name | Variable Type | Min Value | Max Value | Example |
|---------|---------------|---------------|-----------|-----------|---------|
| 1       | reset_flag    | uint8_t       | 1         | 1         | 1       |

### Message Example"

# Good Message

AZ, J, L, 4,\x9a\x99\x01B (IEEE 754 floating point number), YB

This includes the proper AZ and YB suffixes, is sent by and received by members of the team (following their letter address), and converts the float value using struct.pack for uart communication.

