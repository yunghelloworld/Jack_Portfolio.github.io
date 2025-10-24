---
title: Synthbox9000
---

![Product](https://github.com/user-attachments/assets/fbe797b9-0774-46fa-b209-3b60962887ca)
Updated 10/23/25

The Synthbox9000 is a digital synthesizer that interprets MIDI data and outputs audio based upon it. When the processor receives the MIDI data via uart, it parses it into an amplification as well as interpolation algorithm for volume and pitch shifting respectively. After that it reads individual note data and sums it all into a singular buffer, which is then read out to out of the DAC and into a low pass filter to refine the audio data. The audio signals then reada 3.5mm jack that can plugged into with headphones or a speaker.

Here are the PCB layers and schematic diagram detailing the wirings between each component of the system.

# Schematic
<img width="2256" height="1792" alt="Screenshot_59" src="https://github.com/user-attachments/assets/36790214-b152-4850-aac4-3eec2e5dbae7" />
# Top Layer
<img width="2578" height="1792" alt="Screenshot_56" src="https://github.com/user-attachments/assets/c90d3f09-4f54-4f4d-9b36-8dab1c0bd314" />
# Bottom Layer
<img width="2277" height="1811" alt="Screenshot_57" src="https://github.com/user-attachments/assets/6c8fbed0-2c8d-4dbc-b085-496c80a725b1" />
So far, the system is able to output polyphonic audio but is grainy and scratchy when it comes to non-octave values. We expect this is due to either an inefficient algorithm or lack of memory located on the ESP32 flash. We are looking into switching to wavetable synthesis which utilizes shorter samples (saves memory) and an ADSR algorithm for dynamics.
