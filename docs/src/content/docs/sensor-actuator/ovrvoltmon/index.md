---
title: "Overvoltage Monitor (OvrVoltMon)"
description: "Overvoltage Monitor: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

Overvoltage monitor function operates so that when an overvoltage condition occurs on any of the CPU supply voltages the motor inverter operation is shutdown before the CPU can respond.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `OvrVoltMon/src/Sa_OvrVoltMon.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `OvrVoltMon_Per1`


**Notable header dependencies:** `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Sa_OvrVoltMon.h`, `Sa_OvrVoltMon_Cfg.h`

## Documents

- [OverVoltageMonitor Module Design Document](documents/overvoltagemonitor-mdd) — converted from `OvrVoltMon/doc/OverVoltageMonitor_MDD.docx`
- [OvrVoltMon Integration Manual](documents/ovrvoltmon-integration-manual) — converted from `OvrVoltMon/doc/OvrVoltMon_Integration_Manual.docx`

## Repository location

All files live under `OvrVoltMon/` at the repository root.
