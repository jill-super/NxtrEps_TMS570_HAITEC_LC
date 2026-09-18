---
title: "State Output Control (StOpCtrl)"
description: "State Output Control: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `StOpCtrl/src/Ap_StOpCtrl.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `RampLib`
- `StOpCtrl_Per1`


**Notable header dependencies:** `Ap_StOpCtrl_Cfg.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_StOpCtrl.h`

## Documents

- [State Output Control Module Design Document](documents/state-output-control-mdd) — converted from `StOpCtrl/doc/State_Output_Control_MDD.docx`

## Repository location

All files live under `StOpCtrl/` at the repository root.
