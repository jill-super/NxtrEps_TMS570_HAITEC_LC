---
title: "Base Assist Control (Assist)"
description: "Base Assist Control: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Assist Function applies an appropriate level of motor torque based on handwheel torque and vehicle speed.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `Assist/src/Ap_Assist.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `Assist_Per1`


**Notable header dependencies:** `Ap_Assist_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_Assist.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Assist Integration Manual](documents/assist-integration-manual) — converted from `Assist/doc/Assist_Integration_Manual.docx`
- [Assist Module Design Document](documents/assist-mdd) — converted from `Assist/doc/Assist_MDD.docx`

## Repository location

All files live under `Assist/` at the repository root.
