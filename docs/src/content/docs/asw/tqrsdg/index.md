---
title: "Torque Reasonableness Diagnostics (TqRsDg)"
description: "Torque Reasonableness Diagnostics: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Torque Reasonableness Diagnostics software component (TqRsDg) implements part of the electric power steering function on the TMS570 microcontroller.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `TqRsDg/src/Ap_TqRsDg.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `TqRsDg_Init1`
- `TqRsDg_Per1`


**Notable header dependencies:** `Ap_TqRsDg_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_TqRsDg.h`, `filters.h`, `fixmath.h`

## Documents

- [TorqueReasonableDiagnostics](documents/torquereasonablediagnostics) — converted from `TqRsDg/doc/TorqueReasonableDiagnostics.docx`
- [TrqReasonableness Integration Manual](documents/trqreasonableness-integration-manual) — converted from `TqRsDg/doc/TrqReasonableness_Integration_Manual.docx`

## Repository location

All files live under `TqRsDg/` at the repository root.
