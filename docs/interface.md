# Integration Interface

**Status: draft.** Do not treat example values as a finalized protocol. Agree on this file before the PC and Arduino implementations depend on it.

## Vision → PC Communication

Document:

- Whether the output represents one selected target or every detection.
- The detection-valid flag and behavior when no target is found.
- Image width and height, target center, and coordinate units.
- Whether tracking IDs or confidence are required for the MVP.

The image origin is proposed as the top-left corner, with x increasing rightward and y increasing downward. Confirm this convention as a team.

## PC Communication → Arduino

Before implementation, agree on:

| Item | Decision |
| --- | --- |
| Physical link and baud rate | TBD |
| Encoding and field order | TBD |
| Message delimiter | TBD |
| Coordinate units and valid range | TBD |
| Missing or malformed message behavior | TBD |
| Timeout and stop behavior | TBD |

The meeting draft showed a newline-terminated example such as `436,217,1\n`. It is **an example, not an approved wire format**.

## Firmware → Motor/Mechanism

Record the pan and tilt direction conventions, angle limits, neutral position, motor driver or servo pins, and behavior at physical limits before integrated testing.
