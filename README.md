# Zep oddball paradigm

This script presents a train of auditory stimuli. The sounds are presented in
sequences of n (where n = 8 by default) stimuli. In each sequence there is one
odd stimulus - a stimulus with a higher pitch - called the oddball.
At the start of each auditory stimulus a marker is written on the
parallelport.
In oder to support EEG analysis Markers are given to the BioSemi trigger box.
By default the common stimuli get marker 1 and the odds
get marker 2. The marker is written for 5ms after which the parallel port
will return to the default state, where all data bits are low(a marker value
of 0).

# Opening the sound card.
Zep-2.x doesn't like to list the audio out-/inputs in a similar manner to
Zep-1.x. Mostly because the audio libraries used in Zep tranferred from
a highly platform specific library e.g. ALSA (Linux), DirectSound (windows) to 
portaudio in zep 2 which yields nice results on Linux and windows.
However, the line:
        open(PLAYBACK_NUM_CHANNELS, PLAYBACK_SAMPLE_RATE, 3);
in experiment-folder/modules/std_sound_output_device.zm contains a 3 in order
to use the Xonar STX II: Multichannel (hw:1,0).

# Requirements
- Zep-2.4
- a pc with a parallel port.
- a beexybox type B for the responses.
- BioSemi EEG equipment. Or perhaps another brand that works with Triggers/
marker via the parallel port.

# The task
Participants should press a button when they hear an Oddbal stimulus and do
nothing when they hear the common stimulus.

1. welcome
2. practice instruction
3. practice
4. test instruction
5. test
6. Goodbye.

# Author
Maarten Duijndam
