---
title: "Temporal Monitor (TmprlMon)"
description: "Temporal Monitor: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module helps ensure valid execution time for the forward path.  It generates the falling edge of the monitor signal used by an external processor to determine execution time.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `TmprlMon/src/Sa_TmprlMon.c` | implementation |
| `TmprlMon/src/Sa_TmprlMon2.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `TmprlMon_Per1`
- `TmprlMon_Per2`
- `TmprlMon_Per3`
- `TmprlMon_Trns1`
- `TmprlMon_Trns2`
- `TmprlMon2_Per1`


**Notable header dependencies:** `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Sa_TmprlMon.h`, `Rte_Sa_TmprlMon2.h`, `Sa_TmprlMon2_Cfg.h`, `Sa_TmprlMon_Cfg.h`

## Documents

- [Temporal Monitor 2 Module Design Document](documents/temporal-monitor-2-mdd) — converted from `TmprlMon/doc/Temporal_Monitor_2_MDD.docx`
- [Temporal Monitor Integration Manual](documents/temporal-monitor-integration-manual) — converted from `TmprlMon/doc/Temporal Monitor_Integration_Manual.docx`
- [Temporal Monitor Module Design Document](documents/temporal-monitor-mdd) — converted from `TmprlMon/doc/Temporal_Monitor_MDD.docx`

## Repository location

All files live under `TmprlMon/` at the repository root.
