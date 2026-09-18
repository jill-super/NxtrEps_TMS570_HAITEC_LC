---
title: "Electric Power Consumption Monitor (ElePwr)"
description: "Electric Power Consumption Monitor: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module estimates the instantaneous electric power at the input of the control module and the supply current.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `ElePwr/src/Ap_ElePwr.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `ElePwr_Per1`


**Notable header dependencies:** `Ap_ElePwr_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_ElePwr.h`

## Documents

- [ElePwr Integration Manual](documents/elepwr-integration-manual) — converted from `ElePwr/doc/ElePwr_Integration_Manual.docx`
- [Electric Power Consumption Module Design Document](documents/electric-power-consumption-mdd) — converted from `ElePwr/doc/Electric_Power_Consumption_MDD.docx`

## Repository location

All files live under `ElePwr/` at the repository root.
