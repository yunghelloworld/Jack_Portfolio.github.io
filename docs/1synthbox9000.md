---
title: Synthbox9000
---

![Product](https://github.com/user-attachments/assets/fbe797b9-0774-46fa-b209-3b60962887ca)
Updated 11/12/2025

The Synthbox9000 is a digital synthesizer that interprets MIDI data and outputs audio based upon it. When the processor receives the MIDI data via uart, it parses it into an amplification as well as interpolation algorithm for volume and pitch shifting respectively. After that it reads individual note data and sums it all into a singular buffer, which is then read out to out of the DAC and into a low pass filter to refine the audio data. The audio signals then reada 3.5mm jack that can plugged into with headphones or a speaker.

Here are the PCB layers and schematic diagram detailing the wirings between each component of the system.

# Schematic
<img width="2256" height="1792" alt="Screenshot_59" src="https://github.com/user-attachments/assets/3a03cc58-0c71-47f8-a377-a3ab5ea14664" />

# Top Layer
<img width="2578" height="1792" alt="Screenshot_56" src="https://github.com/user-attachments/assets/76453b15-786c-467c-97eb-1cd5b89aaa85" />

# Bottom Layer
<img width="2277" height="1811" alt="Screenshot_57" src="https://github.com/user-attachments/assets/5a88a48e-c53b-4ec3-a748-bb03fa9a8638" />

PCB Project:
[altium.zip](https://github.com/user-attachments/files/23516356/altium.zip)

# Code Writeup

Our project’s code runs on an ESP32 that receives MIDI messages through UART. It synthesizes sample based polyphonic audio, then sends the signal to an external DAC via I2S. main.cpp configures GPIO pins, starts USB serial debugging, mounts File System, instantiates CreateNotes, initializes ring buffer, and launches I2S driver. MIDIParser.cpp decodes the UART messages and creates objects from them. These objects are pushed to CreateNotes, which loads WAVs from the file system. In CreateNotes, math is done on each of the individual notes to determine pitch shifting and position in the ADSR envelope as it is added into individual note buffers. The WAVs are made from single cycle samples in order to save ESP32 memory. Octave pitch shifting is performed with a linear interpolation algorithm by taking the current WAV in flash (e.g., G7) and creating new audio frames by finding the middle point between two existing audio frames. Linear interpolation with octaves was chosen in order to save processing power, as linear interpolation was only effective at synthesizing octaves for us, where frequency is either halved or doubled. Each note is created from only one waveform sample, which is pitch shifted once if necessary and then stored in a buffer. This wave is then looped to create a continuous note. The ADSR envelope is applied by adjusting the amplitude of samples across a time spectrum, with the attack being the initial hit, the decay being the falling amplitude into the sustain phase. The sustain phase gradually fades out until no audio is being processed, unless the user releases the key before the end of the note. When the user lets go of a key, the MIDI sends a NoteOff message, which brings the sustain phase into the release phase, where the note is more quickly suppressed. Further processing is then applied to the notes in the form of vibrato, tremolo, harmonics, noise, and softclipping. These are intended to synthesize depth for the single cycle audio waveforms. Individual note buffers are then summed into a single buffer in the mixer.cpp file. This mixed signal is then streamed to the I2S output, from which the circuit handles the rest.
