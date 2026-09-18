---
title: "Power Limit Function (Current Mode) (PwrLmtFuncCr)"
description: "Power Limit Function (Current Mode): purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module determines an appropriate limit for the system motor torque command based on reasonable output power and system temperature.  It also determines to what degree the system command is being limited.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `PwrLmtFuncCr/src/Ap_PwrLmtFuncCr.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `PwrLmtFuncCr_Init1`
- `PwrLmtFuncCr_Per1`
- `PwrLmtFuncCr_Per2`


**Notable header dependencies:** `Ap_DiagMgr.h`, `Ap_PwrLmtFuncCr_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_PwrLmtFuncCr.h`, `filters.h`, `fixmath.h`, `float.h`, `interpolation.h`

## Documents

- [Power Limit Function CM Integration Manual](documents/power-limit-function-cm-integration-manual) — converted from `PwrLmtFuncCr/doc/Power_Limit_Function_CM_Integration_Manual.docx`
- [Power Limit Function CM Module Design Document](documents/power-limit-function-cm-mdd) — converted from `PwrLmtFuncCr/doc/Power_Limit_Function_CM_MDD.docx`

## Repository location

All files live under `PwrLmtFuncCr/` at the repository root.
