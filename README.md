# UAV Vision Tracker

A four-person project to build a camera-guided, two-axis pan–tilt tracking prototype. The planned system connects camera input and object detection on a PC to serial communication, Arduino motor control, and a physical mechanism.

The repository is at the **project setup stage**. The folders below establish ownership and integration boundaries; they do not imply that the hardware or the full pipeline has been implemented.

## MVP

1. Capture video from a webcam or compatible USB camera.
2. Detect a target and calculate its center in image coordinates.
3. Send the agreed target data from the PC to the Arduino.
4. Drive a two-axis pan–tilt mechanism and demonstrate the integrated response.

The initial target, motor choice, message format, and operating limits still need team agreement. Tracking IDs, advanced vision models, and additional control features can be considered after the MVP works.

## Repository Map

```text
uav-vision-tracker/
├── README.md
├── .gitignore
├── docs/
│   ├── architecture.md
│   ├── interface.md
│   └── decisions.md
├── software/
│   ├── vision/
│   │   └── README.md
│   └── communication/
│       └── README.md
├── firmware/
│   └── arduino/
│       └── README.md
├── hardware/
│   ├── cad/
│   │   └── README.md
│   ├── wiring/
│   │   └── README.md
│   └── bom.md
└── prototypes/
    └── README.md
```

| Area | Responsibility |
| --- | --- |
| [Vision](software/vision/README.md) | Camera input, detection, and target coordinates |
| [PC communication](software/communication/README.md) | Serial encoding and transmission |
| [Arduino firmware](firmware/arduino/README.md) | Message parsing, control logic, and motor output |
| [Hardware](hardware/) | Pan–tilt mechanism, mounting, wiring, and parts |
| [System documents](docs/) | Architecture, shared interfaces, and decisions |
| [Prototypes](prototypes/README.md) | Experiments before they become part of the integrated system |

## Integration Contract

The team should agree on the data exchanged between modules before implementing each part independently. Record the confirmed format, units, coordinate convention, and behavior when detection or communication fails in [docs/interface.md](docs/interface.md). Keep design decisions in [docs/decisions.md](docs/decisions.md).

## Working Together

The four work areas are vision, PC communication, Arduino/motor control, and mechanical design. For changes that affect another area, update the interface document and review the change with the relevant owner. Small branches and pull requests make it easier to integrate and discuss each part.

## Current Status

- Repository structure and planning documents: created.
- Vision, communication, firmware, and hardware implementations: to be added.
- End-to-end camera-to-motor demonstration: pending.

Setup and run commands will be added with the first integrated implementation so they match the files actually committed here.
