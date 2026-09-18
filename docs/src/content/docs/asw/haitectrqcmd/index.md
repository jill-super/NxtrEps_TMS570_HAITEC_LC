---
title: "Haitec Torque Command Interface (HaitecTrqCmd)"
description: "Haitec Torque Command Interface: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This component provides a motor torque command from diagnostic service that is manipulated by a damping curve based on motor velocity. This is intended to help provide system stability when the part is being operated via torque over CAN messages on a test stand or bench.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `HaitecTrqCmd/src/Ap_HaitecTrqCmd.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `HaitecTrqCmd_Init1`
- `HaitecTrqCmd_Per1`
- `HaitecTrqCmd_SCom_StartCtrl`
- `HaitecTrqCmd_SCom_StopCtrl`


**Notable header dependencies:** `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_HaitecTrqCmd.h`, `filters.h`

## Documents

- [HaitecTrqCmd Integration Manual](documents/haitectrqcmd-integration-manual) — converted from `HaitecTrqCmd/doc/HaitecTrqCmd_Integration Manual.doc`
- [HaitecTrqCmd Module Design Document](documents/haitectrqcmd-mdd) — converted from `HaitecTrqCmd/doc/HaitecTrqCmd_MDD.docx`

## Repository location

All files live under `HaitecTrqCmd/` at the repository root.
