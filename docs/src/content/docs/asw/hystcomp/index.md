---
title: "Hysteresis Compensation (HystComp)"
description: "Hysteresis Compensation: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module will calculate a motor torque command to add into the low pass assist torque that will compensate for the hysteresis present in the system.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `HystComp/src/Ap_HystComp.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `MoreCompensation`
- `LessCompensation`
- `CalcAvailComp`
- `HystComp_Init1`
- `HystComp_Per1`


**Notable header dependencies:** `Ap_HystComp_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_HystComp.h`, `filters.h`, `fixmath.h`, `float.h`, `interpolation.h`

## Documents

- [HystComp Integration Manual](documents/hystcomp-integration-manual) — converted from `HystComp/doc/HystComp_Integration_Manual.docx`
- [Hysteresis Compensation Module Design Document](documents/hysteresis-compensation-mdd) — converted from `HystComp/doc/Hysteresis_Compensation_MDD.doc`

## Repository location

All files live under `HystComp/` at the repository root.
