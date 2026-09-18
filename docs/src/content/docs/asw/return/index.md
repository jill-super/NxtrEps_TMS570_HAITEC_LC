---
title: "Return Control (Return)"
description: "Return Control: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This function uses the Absolute Hand Wheel position, Hand Wheel Torque, Hand Wheel Velocity and Vehicle Speed to derive the desired Return Torque command.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `Return/src/Ap_Return.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `Return_Per1`


**Notable header dependencies:** `Ap_Return_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_Return.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Return Module Design Document](documents/return-mdd) — converted from `Return/doc/Return_MDD.docx`

## Repository location

All files live under `Return/` at the repository root.
