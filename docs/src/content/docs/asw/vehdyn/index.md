---
title: "Vehicle Dynamics (VehDyn)"
description: "Vehicle Dynamics: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module calculates HandWheel AutoCentering and determines the Vehicle Dynamics HandWheel Position and Vehicle Dynamics Authority.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `VehDyn/src/Ap_VehDyn.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `Autocenter_f32`
- `VehDyn_Init1`
- `VehDyn_Per1`
- `VehDyn_SCom`
- `VehDyn_Trns1`


**Notable header dependencies:** `Ap_VehDyn_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_VehDyn.h`, `SystemTime.h`, `filters.h`, `fixmath.h`

## Documents

- [Unit-Test Report ((skipped cases) without Power Steering)](documents/index-skipped-withoutps) — converted from `VehDyn/utp/Tessy/report/index_Skipped_WithoutPS.pdf`
- [Unit-Test Report (with Power Steering)](documents/index-withps) — converted from `VehDyn/utp/Tessy/report/index_WithPS.pdf`
- [Unit-Test Report (without Power Steering)](documents/index-withoutps) — converted from `VehDyn/utp/Tessy/report/index_WithoutPS.pdf`
- [VehDyn Integration Manual](documents/vehdyn-integration-manual) — converted from `VehDyn/doc/VehDyn_Integration_Manual.docx`
- [VehDyn Module Design Document](documents/vehdyn-mdd) — converted from `VehDyn/doc/VehDyn_MDD.docx`

## Repository location

All files live under `VehDyn/` at the repository root.
