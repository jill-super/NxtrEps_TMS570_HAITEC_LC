---
title: "Basic Software (BSW)"
description: "AUTOSAR Basic Software: Vector MICROSAR modules, generated configuration, and Texas Instruments memory-stack drivers."
---

The Basic Software is dominated by the Vector MICROSAR delivery (communication, diagnostics, memory, mode management, operating system) plus the generated configuration for this Electronic Control Unit and the Texas Instruments memory-stack drivers. These pages describe roles, repository files and configuration — not the proprietary internals.

## Vector MICROSAR modules

| Module | Long name | Origin |
| --- | --- | --- |
| [`Can`](./can/) | Controller Area Network Driver | Vector (MICROSAR) |
| [`CanIf`](./canif/) | Controller Area Network Interface | Vector (MICROSAR) |
| [`CanSM`](./cansm/) | Controller Area Network State Manager | Vector (MICROSAR) |
| [`CanTp`](./cantp/) | Controller Area Network Transport Protocol | Vector (MICROSAR) |
| [`CanXcp`](./canxcp/) | Controller Area Network Calibration Protocol | Vector (MICROSAR) |
| [`Com`](./com/) | Communication | Vector (MICROSAR) |
| [`ComM`](./comm/) | Communication Manager | Vector (MICROSAR) |
| [`Crc`](./crc/) | Cyclic Redundancy Check Library | Vector (MICROSAR) |
| [`Dcm`](./dcm/) | Diagnostic Communication Manager | Vector (MICROSAR) |
| [`Dem`](./dem/) | Diagnostic Event Manager | Vector (MICROSAR) |
| [`Det`](./det/) | Development Error Tracer | Vector (MICROSAR) |
| [`Dio`](./dio/) | Digital Input Output Driver | Vector (MICROSAR) |
| [`EcuM`](./ecum/) | Electronic Control Unit State Manager | Vector (MICROSAR) |
| [`Gpt`](./gpt/) | General Purpose Timer Driver | Vector (MICROSAR) |
| [`IoHwAb`](./iohwab/) | Input Output Hardware Abstraction | Vector (MICROSAR) |
| [`Mcu`](./mcu/) | Microcontroller Unit Driver | Vector (MICROSAR) |
| [`MemIf`](./memif/) | Memory Abstraction Interface | Vector (MICROSAR) |
| [`NvM`](./nvm/) | Non-Volatile Random Access Memory Manager | Vector (MICROSAR) |
| [`Os`](./os/) | Operating System (OSEK) | Vector (MICROSAR) |
| [`PduR`](./pdur/) | Protocol Data Unit Router | Vector (MICROSAR) |
| [`Port`](./port/) | Port Driver | Vector (MICROSAR) |
| [`VStdLib`](./vstdlib/) | Vector Standard Library | Vector (MICROSAR) |
| [`Vmm`](./vmm/) | Vector Memory Manager | Vector (MICROSAR) |
| [`Wdg`](./wdg/) | Watchdog Driver | Vector (MICROSAR) |
| [`WdgIf`](./wdgif/) | Watchdog Interface | Vector (MICROSAR) |
| [`WdgM`](./wdgm/) | Watchdog Manager | Vector (MICROSAR) |
| [`Xcp`](./xcp/) | Universal Measurement and Calibration Protocol | Vector (MICROSAR) |
| [`_Common`](./common/) | Common Basic Software Files | Vector (MICROSAR) |

## Memory stack (Texas Instruments) and infrastructure

| Module | Long name | Origin |
| --- | --- | --- |
| [`Fee`](./fee/) | Flash EEPROM Emulation | Texas Instruments |
| [`Fls`](./fls/) | Flash Driver (F021 Flash API) | Texas Instruments |
| [Runtime Environment](./runtime-environment/) | MICROSAR Runtime Environment | Vector-generated |
| [Generated configuration](./generated-configuration/) | DaVinci/GENy output (GenData) | Vector-generated |
| [Reference documents](./documents/) | Vector Technical References | Vector |
