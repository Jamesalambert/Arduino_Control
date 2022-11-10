# Arduino_Control

This is a control system designed for operating electric propulsion systems, although it can be easily adapted to very different purposes. Serial is used for comms but UART or CAN is more likely to be used for deployment.

## Language
The Arduino reads bytes from the Serial connection, 4 bytes are sent at a time:
```
|---start_character---|---channel---|---activation---|---end_character---|
```

for example turning channel 4 on would look like this:
```
-41^
```
Turning it off would be done like this
```
-40^
```

# Design
The code implements a finite state machine described in the accompanying pdf.

## Caveats
1. Ensure the transmitting device is set to the same baud rate as the Arduino.
1. Ensure the Arduino and the transmitting device agree on the start and end symbols.
