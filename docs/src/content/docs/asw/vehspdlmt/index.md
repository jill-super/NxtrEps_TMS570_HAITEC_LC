---
title: "Vehicle Speed Limiter (VehSpdLmt)"
description: "Vehicle Speed Limiter: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Vehicle Speed Limiting Function determines a limited assist torque command value as a function of vehicle speed and handwheel position to manage mechanical fatigue near end-of-travel positions.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `VehSpdLmt/src/Ap_VehSpdLmt.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `VehSpdLmt_Per1`


**Notable header dependencies:** `Ap_VehSpdLmt_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_VehSpdLmt.h`, `fixmath.h`, `interpolation.h`

## Documents

- [VehSpdLmt Module Design Document](documents/vehspdlmt-mdd) — converted from `VehSpdLmt/doc/VehSpdLmt_MDD.docx`

## Repository location

All files live under `VehSpdLmt/` at the repository root.
