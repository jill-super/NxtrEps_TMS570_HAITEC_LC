---
title: "Battery Voltage Diagnostics (BVDiag)"
description: "Battery Voltage Diagnostics: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Battery Voltage Diagnostics software component (BVDiag) implements part of the electric power steering function on the TMS570 microcontroller.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `BVDiag/src/Ap_BVDiag.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ApplyHysteresis`
- `ControlTimers`
- `BVDiag_Per1`


**Notable header dependencies:** `Ap_BVDiag_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_BVDiag.h`, `SystemTime.h`, `fixmath.h`

## Documents

- [BVDiag Integration Manual](documents/bvdiag-integration-manual) — converted from `BVDiag/doc/BVDiag_Integration_Manual.docx`
- [Battery Voltage Diagnostics](documents/battery-voltage-diagnostics) — converted from `BVDiag/doc/Battery_Voltage_Diagnostics.doc`

## Repository location

All files live under `BVDiag/` at the repository root.
