---
title: "Stability Compensation (StabilityComp)"
description: "Stability Compensation: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This function provides in-vehicle stability of EPS behavior. To maximize steering feel, the function blends between two different tunings based on vehicle speed and low frequency handwheel torque. Because system gains may get multiplied by various scale factors, either from serial communications or from other software functions, this function provides a second blending feature.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `StabilityComp/src/Ap_StabilityComp.c` | implementation |
| `StabilityComp/src/Ap_StabilityComp2.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ApplyStabilityComp`
- `StabilityComp_Init1`
- `StabilityComp_Per1`
- `ApplyStabilityComp2`
- `StabilityComp2_Init1`
- `StabilityComp2_Per1`


**Notable header dependencies:** `Ap_StabilityComp2_Cfg.h`, `Ap_StabilityComp_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_StabilityComp.h`, `Rte_Ap_StabilityComp2.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Logfile](documents/logfile) — converted from `StabilityComp/tools/logfile.txt`
- [StabilityCompensation Module Design Document](documents/stabilitycompensation-mdd) — converted from `StabilityComp/doc/StabilityCompensation_MDD.docx`
- [StabilityCompensation2 Module Design Document](documents/stabilitycompensation2-mdd) — converted from `StabilityComp/doc/StabilityCompensation2_MDD.docx`

## Repository location

All files live under `StabilityComp/` at the repository root.
