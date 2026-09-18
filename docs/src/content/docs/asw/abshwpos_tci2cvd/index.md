---
title: "Absolute Handwheel Position (AbsHwPos_TcI2cVd)"
description: "Absolute Handwheel Position: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Absolute Hand Wheel Position Function is responsible for determining the steering wheel hand wheel position using either a Turns Counter estimate of motor position during key off and sensorless learnt internal hw position (for eg. Sensorless Vehicle Dynamics, Stored Last Position, Travel Exclusuin, etc) or  I2C digital hw position sensor and sensorless learnt internal hw position.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `AbsHwPos_TcI2cVd/src/Ap_AbsHwPos.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `TrimNotPerfDiag`
- `AbsHwPos_Init1`
- `AbsHwPos_Per1`
- `AbsHwPos_Per2`
- `AbsHwPos_Per3`
- `AbsHwPos_Per4`
- `AbsHwPos_SCom_CustClrTrim`
- `AbsHwPos_SCom_CustSetTrim`
- `AbsHwPos_SCom_NxtClearTrim`
- `AbsHwPos_SCom_NxtSetTrim`


**Notable header dependencies:** `Ap_AbsHwPos_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_AbsHwPos.h`, `filters.h`

## Documents

- [AbsHwPos TcI2cVd Integration Manual](documents/abshwpos-tci2cvd-integration-manual) — converted from `AbsHwPos_TcI2cVd/doc/AbsHwPos_TcI2cVd_Integration_Manual.docx`
- [Absolute Handwheel Position TcI2cVd Module Design Document](documents/absolute-handwheel-position-tci2cvd-mdd) — converted from `AbsHwPos_TcI2cVd/doc/Absolute_Handwheel_Position_TcI2cVd_MDD.docx`
- [Unit-Test Report (with Power Steering)](documents/index-withps) — converted from `AbsHwPos_TcI2cVd/utp/Tessy/report/index_WithPS.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps) — converted from `AbsHwPos_TcI2cVd/utp/Tessy/report/index_WithOutPS.pdf`

## Repository location

All files live under `AbsHwPos_TcI2cVd/` at the repository root.
