# RALLY COPILOT BOARD

This project has been created with the objective to build an aid to rally pilots.
The board allows the pilot to record and later play vocal notes.

The board has five buttons and one switch.
The first two buttons from the left are used to skip a track or play the previous one.
The two buttons on the right are used to manage the playback speed (1x 2x 3x etc).
The red button on the left is used to pause/resume reproduction in playback mode and to start/end recording when in recording mode.
The middle switch is instead used to switch between playback mode and recording mode (ON = PLAYBACK; OFF = RECORD).

The first four buttons are wired through some resistors to create a variable voltage divider. (Wiring schematics in the project folder).
The record button and the mode selection switch are wired independently and are powered through the Arduino's internal pullup resistors.

To play audio we are using a board connected to an Arduino.
The board is capable or reproducing MP3 and WAV files through a 3.5mm audio jack.

# BUTTONS 
(FOR BUTTONS NUMBER REFER TO THE BOARD LAYOUT IMAGE)

1) PREVIOUS TRACK
2) NEXT TRACK
3) SPEED DOWN
4) SPEED UP
5) RECORD/STOP_RECORDING - PLAYBACK/PAUSE
6) MODE SWITCH

# BUTTON WIRING 
(FOR BUTTONS NUMBER REFER TO THE BOARD LAYOUT IMAGE)

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

To learn everything about how to use the recording library read the library page:
https://github.com/TMRh20/TMRpcm/wiki/Advanced-Features#recording-audio

Recommended sample rate: 8kHz

The library samples data using the ADC inside the Arduino. Give it's limited resolution the audio input needs to be amplified to make it reach a level between 0 and 5 volts. For amplifying the signale I chose to use an LM358P rail to rail operational amplifier with a small DC offset to sample the positive and negative side of the incoming signal.

# IMPORTANT NOTES
The mp3 player shield can only read files which names follow the following format => ("trackXXX.mp3" / "trackXXX.wav").

Since the used library isn't capable of returning the number of the track which is currently being played, I wrote the program in such a way to update a variable which keeps the number of the currently playing track every time it plays a new one.

It is also worth to note that the mp3 player module doesn't automatically play the next track on the SD card when a track ends but it just stops.
