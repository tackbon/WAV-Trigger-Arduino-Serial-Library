WAV-Trigger-Arduino-Serial-Library
==================================

WAV Trigger Serial Control Arduino Library

This first preliminary version is written as part of a demo sketch for controlling
the WAV Trigger from an Arduino YUN via a browser interface over wifi. It uses
the AltSoftwareSerial library from PJRC for compatibility with the YUN. For
the time being, if you want to use a hardware serial port, or the native
Arduino SoftwareSerial class, it's easy enough to change. I'll eventually make
this, as well as the baudrate, more easily configured.

This version currently only sends commands TO the WAV Trigger. I've not yet
implemented any functions to receive info FROM the WAV Trigger.

I make no attempt to throttle the amount of messages that are sent. If you send
continuous volume commands at full speed, you risk overflowing the WAV Trigger's
serial input buffer and/or causing clicks in the WAV Triggers audio output due to
excessive serial interrupt processing stealing cycles from audio playback. If you
are connecting a continuous controller that can change rapidly for volume control,
you should use a timer to send changes only every 20 - 50 msecs.
