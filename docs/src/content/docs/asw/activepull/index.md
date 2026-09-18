---
title: "Active Pull Compensation (ActivePull)"
description: "Active Pull Compensation: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module corrects for vehicle pull issues by compensation for both long and short term torque offsets.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `ActivePull/src/Ap_ActivePull.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ActivePull_Init1`
- `ActivePull_Per1`
- `ActivePull_Per2`
- `ActivePull_Per3`
- `ActivePull_SCom_ReadParam`
- `ActivePull_SCom_Reset`
- `ActivePull_SCom_SetLTComp`
- `ActivePull_SCom_SetSTComp`
- `ActivePull_Trns1`


**Notable header dependencies:** `Ap_ActivePull_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_ActivePull.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Active Pull Comp Module Design Document](documents/active-pull-comp-mdd) — converted from `ActivePull/doc/Active_Pull_Comp_MDD.docx`

## Repository location

All files live under `ActivePull/` at the repository root.
