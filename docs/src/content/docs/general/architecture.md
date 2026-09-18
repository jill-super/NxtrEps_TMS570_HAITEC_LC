---
title: "System architecture"
description: "AUTOSAR layering of the steering system and how the parts fit together."
---

## Layered overview

The software follows the classic AUTOSAR layering, implemented for a single Electronic Control Unit
built around the Texas Instruments TMS570LS30316U safety microcontroller:

```text
+---------------------------------------------------------------+  Application Software (ASW)
| Base Assist | Damping | Return | Active Pull | Friction Learning |  ~43 components (Ap_*)
| ... Thermal Duty Cycle ... Vehicle Dynamics ... State Control  |
+---------------------------------------------------------------+
+---------------------------------------------------------------+  Sensor / Actuator (Sa_)
| Handwheel Torque (SENT) | Motor Velocity | Battery Voltage | ... |
+---------------------------------------------------------------+
+----------------------------------------+----------------------+  Complex Device Drivers
| ADC | DMA | SPI | ePWM/NHet | PWM driver | uDiag | NvM proxy |  (CDD)
+----------------------------------------+----------------------+
+---------------------------------------------------------------+  Runtime Environment
| MICROSAR RTE 2.19.1 (generated): Rte.c/h, component contracts |
+---------------------------------------------------------------+
+---------------------------------------------------------------+  Basic Software (BSW)
| Services: Os OSEK | EcuM | Dem | Dcm | NvM | WdgM | DiagMgr-adjacent |
| Communication: Com | ComM | PduR | CanIf | CanSM | CanTp | CanXcp | Xcp |
| Memory: MemIf | Fee (TI) | Fls (TI F021 API)                        |
| ECU Abstraction: IoHwAb | System: Det | Crc | VStdLib | Wdg/ WdgIf      |
+---------------------------------------------------------------+
+---------------------------------------------------------------+  Microcontroller (MCAL)
| Dio | Port | Gpt | Mcu | Adc (HW) | CAN (DCAN) | Flash | RAM       |
+---------------------------------------------------------------+
  Texas Instruments TMS570LS30316U (ARM Cortex-R4F, Hercules family)
```

- [Application Software](../asw/) holds the steering control strategy.
- [Sensor and Actuator Components](../sensor-actuator/) condition raw signals into physical quantities.
- [Complex Device Drivers](../cdd/) encapsulate direct hardware access (conversion, direct memory access,
  serial links, motor PWM, microcontroller self-tests).
- The **Runtime Environment** (generated, Vector MICROSAR RTE 2.19.1) connects application components through
  ports; see [Runtime Environment](../bsw/runtime-environment/).
- [Basic Software](../bsw/) is the Vector MICROSAR delivery plus generated configuration and the
  Texas Instruments memory-stack drivers.

## Safety concept

The system targets demanding automotive use (ISO 26262 ASIL D process heritage from the README):

- **Firewall monitors** (`AssistFirewall`, `DampingFirewall`, `ReturnFirewall`, `EtDmpFw`) bound the outputs of
  their sibling functions independently.
- **Plausibility and reasonableness checks** (`TqRsDg`, `ComplErr`, `Polarity`) detect inconsistent torque paths.
- **Temporal supervision** (`TmprlMon`, `ShtdnMech`) and the AUTOSAR [Watchdog Manager](../bsw/wdgm/) supervise
  program flow and deadlines.
- **Microcontroller self-diagnostics** (`TMS570_uDiag`: clock monitor, ECC, ESM, FPU, flash test) detect
  hardware faults.
- **Controlled shutdown paths** (`CtrldDisShtdn`, `ShtdnMech`, `Gsod`) force a safe state on severe faults.

## Data flow (simplified)

```text
Handwheel Torque (SENT) ──> Signal Conditioning ──> Base Assist ──> Firewall ──> Motor Control (Current Mode)
Vehicle Speed ────────────> Assist curves ────────> Damping ──────> ... ──────> Space Vector PWM Driver
Battery / Temperatures ───> Thermal Duty Cycle ──> Power limits ──> ... ──────> 3-phase motor
Diagnostics <──> Diagnostic Manager <──> Dem/Dcm <──> CAN vehicle bus
Calibration/measurement <──> XCP over CAN <──> host tools
Persistent data <──> Non-Volatile Memory Manager/Proxy <──> Fee/Fls <──> on-chip flash
```
