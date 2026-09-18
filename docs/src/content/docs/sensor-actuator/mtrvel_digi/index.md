---
title: "Digital Motor Velocity Sensing (MtrVel_Digi)"
description: "Digital Motor Velocity Sensing: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This diagram describes the functional characteristics and data flow of a given function.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `MtrVel_Digi/src/Sa_MtrVel.c` | implementation |
| `MtrVel_Digi/src/Sa_MtrVel2.c` | implementation |
| `MtrVel_Digi/src/Sa_MtrVel3.c` | implementation |
| `MtrVel_Digi/include/Sa_MtrVel.h` | public interface |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `CalcCoarseVel`
- `MtrVelBlend`
- `RegressionFit`
- `MtrVel_Init`
- `MtrVel_Per1`
- `MtrVel_Per2`
- `MtrVel2_Init`
- `MtrVel2_Per1`
- `MtrVel2_Per2`
- `MtrVel3_Init`
- `MtrVel3_Per1`


**Public interface declarations** (from headers):

- `UNC`


**Notable header dependencies:** `CalConstants.h`, `Float.h`, `GlobalMacro.h`, `MemMap.h`, `MtrVel_Cfg.h`, `Rte_Sa_MtrVel.h`, `Rte_Sa_MtrVel2.h`, `Rte_Sa_MtrVel3.h`, `Sa_MtrVel.h`, `Sa_MtrVel2_Cfg.h`, `Sa_MtrVel_Cfg.h`, `filters.h`, `fixmath.h`, `float.h`, `interpolation.h`

## Documents

- [Motor Velocity Integration Manual](documents/motor-velocity-integration-manual) — converted from `MtrVel_Digi/doc/Motor Velocity_Integration_Manual.docx`
- [MotorVelocity Module Design Document](documents/motorvelocity-mdd) — converted from `MtrVel_Digi/doc/MotorVelocity_MDD.doc`
- [MotorVelocity2 Module Design Document](documents/motorvelocity2-mdd) — converted from `MtrVel_Digi/doc/MotorVelocity2_MDD.doc`
- [MotorVelocity3 Module Design Document](documents/motorvelocity3-mdd) — converted from `MtrVel_Digi/doc/MotorVelocity3_MDD.doc`
- [Unit-Test Report (with Power Steering)](documents/index-withps) — converted from `MtrVel_Digi/utp/Tessy/report/MtrVel_Digi/index_WithPS.pdf`
- [Unit-Test Report (with Power Steering)](documents/index-withps-2) — converted from `MtrVel_Digi/utp/Tessy/report/MtrVel_Digi2/index_WithPS.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps) — converted from `MtrVel_Digi/utp/Tessy/report/MtrVel_Digi/index_WithOutPS.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps-2) — converted from `MtrVel_Digi/utp/Tessy/report/MtrVel_Digi2/index_WithOutPS.pdf`

## Repository location

All files live under `MtrVel_Digi/` at the repository root.
