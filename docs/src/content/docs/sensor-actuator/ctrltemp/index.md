---
title: "Controller Temperature Monitor (CtrlTemp)"
description: "Controller Temperature Monitor: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module monitors the controller’s temperature sensor output, filters that output, and checks whether the output is within a lower and upper limit.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `CtrlTemp/src/Sa_CtrlTemp.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `CtrlTemp_Init1`
- `CtrlTemp_Per1`
- `CtrlTemp_Per2`


**Notable header dependencies:** `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Sa_CtrlTemp.h`, `Sa_CtrlTemp_Cfg.h`, `filters.h`, `fixmath.h`

## Documents

- [Controller Temperature Module Design Document](documents/controller-temperature-mdd) — converted from `CtrlTemp/doc/Controller_Temperature_MDD.docx`
- [CtrlTemp Integration Manual](documents/ctrltemp-integration-manual) — converted from `CtrlTemp/doc/CtrlTemp_Integration_Manual.docx`

## Repository location

All files live under `CtrlTemp/` at the repository root.
