---
title: "Frequency Sweep Diagnostics (Sweep)"
description: "Frequency Sweep Diagnostics: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

The library and functions / Macros that are called by the various sub modules are identified below,

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `Sweep/src/Ap_Sweep.c` | implementation |
| `Sweep/src/Ap_Sweep2.c` | implementation |
| `Sweep/include/Ap_Sweep.h` | public interface |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `Sweep_Init`
- `Sweep_Per1`
- `Sweep2_Per1`


**Notable header dependencies:** `Ap_Sweep.h`, `Ap_Sweep2_Cfg.h`, `Ap_Sweep_Cfg.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_Sweep.h`, `Rte_Ap_Sweep2.h`, `fixmath.h`

## Documents

- [Sweep1 Module Design Document](documents/sweep1-mdd) — converted from `Sweep/doc/Sweep1_MDD.docx`
- [Sweep2 Module Design Document](documents/sweep2-mdd) — converted from `Sweep/doc/Sweep2_MDD.docx`

## Repository location

All files live under `Sweep/` at the repository root.
