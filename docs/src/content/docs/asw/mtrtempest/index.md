---
title: "Motor Temperature Estimation (MtrTempEst)"
description: "Motor Temperature Estimation: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module details out the estimation functions (first order lead lag filters) used to estimate the controller Silicon, motor magnet and the motor copper winding temperatures based on the measured substrate temperature and the variation in ambient temperature.  The variation in ambient temperature is added as a correction term to the outputs of the lead lag filters and is separate for Si, Magnet and Cu.  The correction term representing the variation of temperature above ambient is based off the measured motor current representing the Q-and D axes and uses a first order low pass filter struct

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `MtrTempEst/src/Ap_MtrTempEst.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `LeadLagFilt`
- `LeadLagFiltInit`
- `AssMechFiltInit`
- `MtrTempEst_Init1`
- `MtrTempEst_Per1`


**Notable header dependencies:** `Ap_MtrTempEst_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_MtrTempEst.h`, `filters.h`, `fixmath.h`

## Documents

- [Motor Temperature Estimation Integration Manual](documents/motor-temperature-estimation-integration-manual) — converted from `MtrTempEst/doc/Motor_Temperature_Estimation_Integration_Manual.docx`
- [Motor Temperature Estimation Module Design Document](documents/motor-temperature-estimation-mdd) — converted from `MtrTempEst/doc/Motor_Temperature_Estimation_MDD.docx`

## Repository location

All files live under `MtrTempEst/` at the repository root.
