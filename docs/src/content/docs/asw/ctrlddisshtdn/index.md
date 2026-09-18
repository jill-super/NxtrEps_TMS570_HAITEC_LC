---
title: "Controlled Disable and Shutdown (CtrldDisShtdn)"
description: "Controlled Disable and Shutdown: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The Controlled Disable Damping Shutdown method is used for torque sensor failures.  When the torque sensor fails, an output torque is computed based on motor velocity to reduce the amount of “handwheel kick” perceived by the driver.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `CtrldDisShtdn/src/Ap_CtrldDisShtdn.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `CtrldDisShtdn_Per1`


**Notable header dependencies:** `Ap_CtrldDisShtdn_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_CtrldDisShtdn.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Controller Disable Module Design Document](documents/controller-disable-mdd) — converted from `CtrldDisShtdn/doc/Controller_Disable_MDD.docx`

## Repository location

All files live under `CtrldDisShtdn/` at the repository root.
