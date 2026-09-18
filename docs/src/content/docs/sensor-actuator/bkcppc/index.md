---
title: "Bulk Capacitor Pre-Charge Control (BkCpPc)"
description: "Bulk Capacitor Pre-Charge Control: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module handles precharging of the bulk capacitor during initialization.  It is part of a larger initialization sequence, along with motor driver diagnostics and temporal monitor.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `BkCpPc/src/Sa_BkCpPc.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `BkCpPc_Per1`
- `BkCpPc_Trns1`
- `BkCpPc_Trns2`
- `CapPcDcStub_OP_SET`


**Notable header dependencies:** `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Sa_BkCpPc.h`, `Sa_BkCpPc_Cfg.h`

## Documents

- [Bulk Cap Precharge Module Design Document](documents/bulk-cap-precharge-mdd) — converted from `BkCpPc/doc/Bulk_Cap_Precharge_MDD.docx`

## Repository location

All files live under `BkCpPc/` at the repository root.
