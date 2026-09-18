---
title: "End-of-Travel Actuator Management (EOTActuatorMng)"
description: "End-of-Travel Actuator Management: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The end of travel actuator management limit reduces the level of assist from the motor as the steering system approaches the mechanical end of stop of the system.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `EOTActuatorMng/src/Ap_EOTActuatorMng.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `EOTDetermination`
- `EOTOrigImpact`
- `SES_DetLmtPos`
- `SES_CalcExitGain`
- `SES_StateCtrl`
- `SES_CalcEnterGain`
- `SES_CalcEOTGain`
- `SES_FiltEOTGain`
- `SES_CalcEOTDamp`
- `EOTActuatorMng_Per1`


**Notable header dependencies:** `Ap_EOTActuatorMng_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_EOTActuatorMng.h`, `filters.h`, `fixmath.h`, `fpmtype.h`, `interpolation.h`

## Documents

- [EOTActuatorManagement Integration Manual](documents/eotactuatormanagement-integration-manual) — converted from `EOTActuatorMng/doc/EOTActuatorManagement_Integration_Manual.docx`
- [End Of Travel Actuator Management Module Design Document](documents/end-of-travel-actuator-management-mdd) — converted from `EOTActuatorMng/doc/End_of_Travel_Actuator_Management_MDD.docx`

## Repository location

All files live under `EOTActuatorMng/` at the repository root.
