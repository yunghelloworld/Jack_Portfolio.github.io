---
title: Synthbox9000
---

![Product](https://github.com/user-attachments/assets/fbe797b9-0774-46fa-b209-3b60962887ca)
Updated 10/23/25

The Synthbox9000 is a digital synthesizer that interprets MIDI data and outputs audio based upon it. When the processor receives the MIDI data via uart, it parses it into an amplification as well as interpolation algorithm for volume and pitch shifting respectively. After that it reads individual note data and sums it all into a singular buffer, which is then read out to out of the DAC and into a low pass filter to refine the audio data. The audio signals then reada 3.5mm jack that can plugged into with headphones or a speaker.

Here are the PCB layers and schematic diagram detailing the wirings between each component of the system.

# Schematic

# Top Layer

# Bottom Layer

So far, the system is able to output polyphonic audio but is grainy and scratchy when it comes to non-octave values. We expect this is due to either an inefficient algorithm or lack of memory located on the ESP32 flash. We are looking into switching to wavetable synthesis which utilizes shorter samples (saves memory) and an ADSR algorithm for dynamics.
