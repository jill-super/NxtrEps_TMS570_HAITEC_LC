---
title: "Sensor and Actuator Components (Sa_)"
description: "Sensor/actuator-near application software components (Sa_*) at the boundary between application and hardware."
---

Sensor/actuator software components (`Sa_*`) sit at the boundary between the application and the hardware: they condition raw sensor signals (handwheel torque over SENT, motor position, battery voltage, temperatures) and drive actuators, exposing clean physical signals to the application layer.

## Modules in this layer (9)

| Component | Directory | Origin |
| --- | --- | --- |
| [Bulk Capacitor Pre-Charge Control](./bkcppc/) | `BkCpPc` | Custom (in-house) |
| [Common Motor Current Measurement](./cmmtrcurr/) | `CmMtrCurr` | Custom (in-house) |
| [Controller Temperature Monitor](./ctrltemp/) | `CtrlTemp` | Custom (in-house) |
| [Digital Handwheel Torque via SENT](./dighwtrqsent/) | `DigHwTrqSENT` | Custom (in-house) |
| [Digital Motor Sensor Bridge](./digmsb/) | `DigMSB` | Custom (in-house) |
| [Digital Motor Velocity Sensing](./mtrvel_digi/) | `MtrVel_Digi` | Custom (in-house) |
| [Overvoltage Monitor](./ovrvoltmon/) | `OvrVoltMon` | Custom (in-house) |
| [Shutdown Mechanisms](./shtdnmech/) | `ShtdnMech` | Custom (in-house) |
| [Temporal Monitor](./tmprlmon/) | `TmprlMon` | Custom (in-house) |
