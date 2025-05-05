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
| OLED Display      | S       |
| Actuator          | J       |
| Broadcast (All)   | X       |

---

## Messages Received

### Message Type 1: Game Start

The OLED subsystem (Shane) alerts the actuator subsystem when the game has started.

| Byte(s) | Variable Name    | Variable Type | Min Value | Max Value | Example |
|---------|------------------|---------------|-----------|-----------|---------|
| 1        | messagetypeone  | char          | 1         |   1         |  1    |
| 2        | gamestart      | char           | 0         | 1           | 1     |

### Message Type 2: Extend Actuator
  
The OLED subsystem (Shane) sends the actuator subsystem a 0 or a 1. The 0 stops the actuator, the 1 tells the actuator to extend.

| Byte(s) | Variable Name    | Variable Type | Min Value | Max Value | Example |
|---------|------------------|---------------|-----------|-----------|---------|
| 1        | messagetypetwo  | char         | 2         |   2         |  2       |
| 2        | extendactuator  | char           | 0        | 1           | 1  |

---

## Messages Sent/Broadcasted

### Message Type 3: Change Value
 
Upon receiving a message to extend the actuator, the actuator will extend then wait a second before telling the OLED subsystem to change to a different target value.

| Byte(s) | Variable Name    | Variable Type | Min Value | Max Value | Example |
|---------|------------------|---------------|-----------|-----------|---------|
| 1        | messagetypethree  | char       | 3        |   3        |  3      |
| 2    | changevalue  | char         | 0            | 1             | 1        |

### Message Type 4: Victory/Reset

This command tells the actuator to either extend or retract. The actuator extends when the pressure input equals the target pressure and retracts if the target is missed within time limit.

| Byte(s) | Variable Name | Variable Type | Min Value | Max Value | Example |
|---------|---------------|---------------|-----------|-----------|---------|
| 1       | messagetypefour | char   | 4         | 4          | 4      |
| 2       | resetflag    | char     | 0         | 1         | 1       |

