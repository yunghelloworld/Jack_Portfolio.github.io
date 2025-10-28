---
title: Multi-Board Embedded System Game
---

![440505804-1f0ceffa-6928-42a8-9292-84dbe1051548](https://github.com/user-attachments/assets/0a3cad9a-d469-4523-98cb-f36a334c22a7)

This is an academic project where I worked with a team mate to create a interactive game where a user changes the state of an actuator based upon a series of button inputs. The user is given a challenge to balance an actuator through giving it the correct position, based upon two push buttons to control forward and reverse motion. The display would graphically tell the user where to position the actuator which would score the user a point. After a certain amount of points, the actuator's position resets and the the display showcases a victory screen. The two boards would communicate to each other using a daisy chain that would provide RX and TX as well and ground and power to both subsystems. Each member created their board with a budget of 50 dollars and individual code that would execute a function and communicate with RX and TX to the other subsystems.

Originally this project was designed to be a pitch recreation game, where the display showed a desired frequency and an actual frequency represented by a horizontal line (desired) and a bar going up and down (actual). The user would sing the pitch into the microphone and when reached for a certain amount of time, would activate the actuator to move forward a little and reset the desired frequency position. After the actuator moves far enough, it would reset its position and display the victory screen on the display. This was not achieved due one team member being banned from campus, and the other team member not being able to contribute, depriving us of multiple subsytems necessary to finish this concept. Despite this, my and my other team mate were able to create a functional game using our individual assigned subsystems within the project deadline.

Here are the final diagrams for our project:

# My Schematic
<img width="1162" height="860" alt="433014086-c3405c84-6338-42e2-b3a5-a182e1f01f06 (1)" src="https://github.com/user-attachments/assets/76075da1-11ae-4cc1-a5e1-487b35432427" />

# My PCB Top Layer
<img width="948" height="674" alt="440073768-7dea54d6-c8b3-4bd8-8218-05ad9ac733f5" src="https://github.com/user-attachments/assets/800d1d79-4f8a-4bb2-9daa-a24c49a3e22f" />

# My PCB Bottom Layer
<img width="951" height="677" alt="440073788-c84e5472-968a-4ab8-b1ad-a87684671a96" src="https://github.com/user-attachments/assets/58821b79-5464-43a6-aea4-e5ebfc6c6943" />

# Block Diagram
<img width="1511" height="641" alt="436682010-d6e47f94-231a-4d55-a046-69b31c67baba" src="https://github.com/user-attachments/assets/19d1fad2-95f9-476b-9104-201d32d12cba" />
