---
title: "Complex Device Drivers (CDD)"
description: "Hardware-near drivers and complex drivers (Cd_*, peripheral and microcontroller drivers)."
---

Complex device drivers (`Cd_*` and peripheral drivers) access the TMS570 hardware directly where the standardised microcontroller abstraction is not sufficient: conversion sequencing, direct memory access, serial links, pulse-width modulation, non-volatile memory access and microcontroller self-supervision.

## Modules in this layer (10)

| Component | Directory | Origin |
| --- | --- | --- |
| [Analog-to-Digital Converter Driver](./adc/) | `Adc` | Custom (in-house) |
| [Direct Memory Access Driver](./dma/) | `Dma` | Custom (in-house) |
| [Enhanced PWM and High-End Timer Driver](./epwm/) | `ePWM` | Custom (in-house) |
| [Motor Driver and Phase Diagnostics](./svdiag/) | `SVDiag` | Custom (in-house) |
| [Non-Volatile Memory Manager](./nvmmgr/) | `NvMMgr` | Custom (in-house) |
| [Non-Volatile Memory Proxy](./nvmproxy/) | `NvMProxy` | Custom (in-house) |
| [Serial Peripheral Interface Driver](./spinxt/) | `SpiNxt` | Custom (in-house) |
| [Space Vector PWM Driver (Current Mode)](./svdrvr_cm/) | `SVDrvr_CM` | Custom (in-house) |
| [TMS570 Microcontroller Diagnostics](./tms570_udiag/) | `TMS570_uDiag` | Custom (in-house) |
| [TMS570 Startup Code](./tms570_startup/) | `TMS570_Startup` | Custom (in-house) |
