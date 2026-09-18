---
title: "Shutdown Mechanisms (ShtdnMech)"
description: "Shutdown Mechanisms: purpose, files, interfaces and documents."
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
| `ShtdnMech/src/Sa_ShtdnMech.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ShtdnMech_Per1`


**Notable header dependencies:** `MemMap.h`, `Rte_Sa_ShtdnMech.h`, `Sa_ShtdnMech_Cfg.h`, `n2het_regs.h`

## Documents

- [Shutdown Mechanisms Module Design Document](documents/shutdown-mechanisms-mdd) — converted from `ShtdnMech/doc/Shutdown_Mechanisms_MDD.docx`

## Repository location

All files live under `ShtdnMech/` at the repository root.
