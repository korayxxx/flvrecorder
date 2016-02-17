# FLVRecorder #
The purpose of this revolutionary new class is to record a stream of BitmapData to a FLV-file, because writing directly, and especially the converting-BitmapData-to-ByteArrays-with-byteshifting-part, made everything run shaky. I solved that issue by saving the BitmapData to a temporary file on the system. This to protect your RAM from overloading, and when done recording, the class converts that temporary file to an FLV-file.

For developing comforts, I build in a few events as well, when recording starts and stops, and an event while saving, with an indication of your progress.

The class offers the user to record via inputting BitmapData, Bitmaps and even your custom components, Flex component, like your VideoDisplay and also Flash components, like the FLVPlayBack or your custom Sprites and MovieClips.

The class does not yet support adding sound to the flv-file, this is the next step of development, to enable sound recording and add sound to the flv-file.

# AirCam #
As a proof-of-concept, I built a small application that enables you to record your webcam and saved it on your desktop as an flv-file.

To view the source used in this project, right-click somewhere, and choose view source.

The FLVRecorder and all related classes are open source, they are not fully tested and may contain bugs.
I’m happy to share it with the community, use them, play with them and certainly enhance them!

# Usage #
These classes are NOT FOR COMMERCIAL USE, meaning they cannot be used for commercial projects other than projects for/from BoulevArt nv.