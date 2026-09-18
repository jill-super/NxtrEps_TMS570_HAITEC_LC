---
title: "High Load Stall Management (HiLoadStall)"
description: "High Load Stall Management: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The High Load Stall Thermal Management algorithm protects the system from prolonged intervals of high assist torque at near-stall conditions.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `HiLoadStall/src/Ap_HiLoadStall.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `HiLoadStall_Per1`


**Notable header dependencies:** `Ap_HiLoadStall_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_HiLoadStall.h`, `filters.h`, `fixmath.h`, `interpolation.h`

## Documents

- [HiLoadStall Module Design Document](documents/hiloadstall-mdd) — converted from `HiLoadStall/doc/HiLoadStall_MDD.docx`
- [Logfile](documents/logfile) — converted from `HiLoadStall/tools/logfile.txt`

## Repository location

All files live under `HiLoadStall/` at the repository root.
