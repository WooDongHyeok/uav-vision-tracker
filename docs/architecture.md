# System Architecture

## Planned MVP Flow

```text
Camera → PC vision → PC serial link → Arduino firmware → motor driver/servo → pan–tilt mechanism
```

The PC reads video, detects the target, and calculates image coordinates. The communication module sends an agreed message to the Arduino. Firmware parses the message and drives the two axes within the limits established by the hardware team.

## Module Boundaries

| Module | Input | Output | Owner area |
| --- | --- | --- | --- |
| Vision | Camera frames | Target detection and coordinates | `software/vision/` |
| PC communication | Agreed target data | Serial message | `software/communication/` |
| Firmware | Serial message | Motor commands | `firmware/arduino/` |
| Mechanism | Motor motion | Camera pan and tilt | `hardware/` |

See [interface.md](interface.md) for fields and conventions once they are agreed. The camera model, board, motor type, and mounting details remain open decisions.
