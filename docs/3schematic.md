---
title: Schematic/PCB/BOM
tags:
- tag1
- tag2
---


## Schematic/PCB

### Schematic

![UpdatedSchematic](https://github.com/user-attachments/assets/c3405c84-6338-42e2-b3a5-a182e1f01f06)

[UpdatedSchematic.pdf](https://github.com/user-attachments/files/19718013/UpdatedSchematic.pdf)

This schematic includes all the basic circuity needed to run 12V to an actuator while simultaneously providing 3.3V to necessary logic supplies. The voltage regulator is crucial in providing this. Necessary inductors and capacitors are included to induce stability in the voltage regulator. Jumpers, headers, pushbuttons, and LEDs are included to test connectivity and other debugging. EN and BOOT connected to 3.3V with a pull-up and a pushbutton which can pull it to GND. All SPI pins are connected to the microcontroller so it can control all the logic the motordriver receives. The microcontroller will send data through the TX pin and receive through the RX pin, connected to the 8 pin daisy chain connector designed to communicate with the team. The received data will cause the microcontroller to send a signal to the motor driver which will extend or retract the actuator. This will be used so the actuator becomes a progress bar for the user to indicate how close they are to winning the game.

## PCB

### Top

![TOP](https://github.com/user-attachments/assets/7dea54d6-c8b3-4bd8-8218-05ad9ac733f5)

### Bottom

![BOTTOM](https://github.com/user-attachments/assets/c84e5472-968a-4ab8-b1ad-a87684671a96)

[UpdatedEGR314JackSubsystem.zip](https://github.com/user-attachments/files/19037228/EGR314JackSubsystem.zip)

### Gerber

[PCBArt.zip](https://github.com/user-attachments/files/20019133/PCBArt.zip)

## Version 2.0

Working on this schematic extensively, I have learned a decent amount of things about schematic and PCB design. To start with the basics, I would have included a more basic pushbutton instead of a pushbutton you would have to push twice. It is not a significant change, but it reflects the devkit version's design more and is more intuitive to work with. Other things I would add would be a greater abundance of headers and jumpers. I originally was not sure how exactly they were supposed to function, and just thought it would clutter up my board, but after gaining knowledge of proper ways to debug boards and reroute signals and attach outside components, I became very aware of the potential they have within the system. I included a few on extraneous GPIO pins as test points, but if I were to redesign it, I would have put a jumper on nearly all my signal pins, especially the ones that connect to my motordriver. When I first printed the board, half of my motordriver's pads were backwards, which meant there had to be a lot of jumper wires attached to the pins that would've been backwards. This was a great struggle, as the surface mount motordriver I had purchased was very small, with pin widths being just over a millimeter. Having to bend those pins up and attach wires to their tiny surfaces without accidentally jumping adjacent took much longer and was a lot more stressful and dangerous to the system than if i had just included headers to jump pins to their correct locations again. I would also utilize a better USB component, as the vertical facing USB was scary to use compared to a horizontal facing one which would have more stability. I would also tried to have get a larger motordriver and a larger diode, as they were hard to solder on by hand. I would also try to include a silkscreen next time, because it was hard to gauge the size of the components outside of the pins, which made the inductor hard to fit in on the board with the rest of the voltage reglator circuit. I would try to be more economical but safe with the spacing, so make the layout more compact and easy to understand. I would make the vias larger in diameter, so that way they could be used as header holes too if necessary. I would also put the pins connecting the motordriver outs to the actuator closer together. I had placed them fart apart, but realized the wires of my actuator were locked togther by the connector, meaning I would have to use extra jumpers to connect it, making it less resource efficient. I would also space out the non-dedicated pins more, so if I accidentally shorted pins while soldering, it would be mostly irrelevant as the utilized GPIO pins would not be interfered with.

## Bill of Materials

![Bill of Materials](https://github.com/user-attachments/assets/dd65f450-a2be-45d4-a92f-9911e784e9a7)

[FinalBillOfMaterials - Purchase Request.pdf](https://github.com/user-attachments/files/20019168/FinalBillOfMaterials.-.Purchase.Request.pdf)

