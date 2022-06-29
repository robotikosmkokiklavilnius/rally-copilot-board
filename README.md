# RALLY COPILOT BOARD
This project has been created with the opbjective to build an aid to rally pilots.
The board allows the pilot to record and later play vocal notes.

The board is made by five buttons and one switch.
The first two buttons from the right are used to skip a track or play the previous one.
The two buttons on the right are used to manage the playback speed (1x 2x 3x etc).
The red button on the left is used to pause/resume reproduction in playback mode and to start/end recording when in recording mode.
The middle switch is instead used to switch between playback mode and recording mode (ON = PLAYBACK; OFF = RECORD).

The first four buttons are wired through some resistors to create a variable voltage divider. (Wiring schematics in the project folder).
The record button and the mode selection switch are wired independently.

To play audio we are using a board connected to an Arduino.
The board is capable or reproducing MP3 and WAV files through a 3.5mm audio jack.

# BUTTONS (REFER TO BOARD IMAGE)

1) PREVIOUS TRACK
2) NEXT TRACK
3) SPEED DOWN
4) SPEED UP
5) RECORD/STOP_RECORDING - PLAYBACK/PAUSE
6) MODE SWITCH

# BUTTON WIRING 

1 TO 4 WIRED IN SERIES = PIN A0

5 = PIN 10

6 = PIN 5


# AUDIO PLAYBACK
(these recordings are used by the arduino to comunicate with the user)

track000.mp3 "RECORDING"

track001.mp3 "STOPPED RECORDING"

track002.mp3 "RECORDINGS LIMIT REACHED"

# SPEED SELECTION
  
The mp3 player library allow to set the speed by adjusting an integer (0=1x 1=1x 2=2x 3=3x).
The libray allows to modify the bitrate so it is theoretically possible to finely adjust the bitrate but I still haven't tested this possibility.

# AUDIO RECORDING
Recommended sample rate 8kHz

The library samples data using the ADC inside the Arduino. Give it's limited resolution the audio input needs to be amplified to make it reach a level between 0 and 5 volts. For amplifying the signale I chose to use an LM358 rail to rail operational amplifier with a small offset to sample the positive and negative side of the incoming signal.



# IMPORTANT NOTES
The mp3 player shield can read files which names follow this format (trackXXX.mp3 / trackXXX.wav)
