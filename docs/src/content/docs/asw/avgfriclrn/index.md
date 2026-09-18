---
title: "Average Friction Learning (AvgFricLrn)"
description: "Average Friction Learning: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module estimates the gear friction changes from the baseline friction and provides compensation.  It is based on the column torque and handwheel angle.  It is primarily active at higher speeds.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `AvgFricLrn/src/Ap_AvgFricLrn.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `LoadBuffer`
- `HwAngConstraint`
- `HwVelConstraint`
- `VehSpdConstraint`
- `FricLearning`
- `BaselineMode`
- `ClearMode`
- `AvgFricLrn_Init1`
- `AvgFricLrn_Per1`
- `AvgFricLrn_SCom_GetEOLFric`
- `AvgFricLrn_SCom_GetOffsetOutputDefeat`
- `AvgFricLrn_SCom_GetSelect`
- `AvgFricLrn_SCom_InitLearnedTables`
- `AvgFricLrn_SCom_ResetToZero`
- `AvgFricLrn_SCom_SetEOLFric`
- `AvgFricLrn_SCom_SetOffsetOutputDefeat`
- `AvgFricLrn_SCom_SetSelect`
- `AvgFricLrn_Trns1`


**Notable header dependencies:** `Ap_AvgFricLrn_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_AvgFricLrn.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Average Friction Learning Module Design Document](documents/average-friction-learning-mdd) — converted from `AvgFricLrn/doc/Average_Friction_Learning_MDD.docx`
- [AvgFricLrn Integration Manual](documents/avgfriclrn-integration-manual) — converted from `AvgFricLrn/doc/AvgFricLrn_Integration_Manual.docx`

## Repository location

All files live under `AvgFricLrn/` at the repository root.
