# Rally-copilot-board
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
