---
title: "Damping Control (Damping)"
description: "Damping Control: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

Damping function computes the Total damping Torque. The total damping command is calculated from two terms, Active Damping Term and the HPS Damping Command.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `Damping/src/Ap_Damping.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `MtrVelDepDampScale`
- `HPSDampingFn`
- `Damping_Init1`
- `Damping_Per1`


**Notable header dependencies:** `Ap_Damping_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_Damping.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [Damping Integration Manual](documents/damping-integration-manual) — converted from `Damping/doc/Damping_Integration_Manual.docx`
- [Damping Module Design Document](documents/damping-mdd) — converted from `Damping/doc/Damping_MDD.docx`

## Repository location

All files live under `Damping/` at the repository root.
