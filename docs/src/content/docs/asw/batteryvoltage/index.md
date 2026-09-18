---
title: "Battery Voltage Sensing (BatteryVoltage)"
description: "Battery Voltage Sensing: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module is responsible for applying voltage and time based hysteresis to the battery voltage to determine over voltage and low voltage faults.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `BatteryVoltage/src/Ap_BatteryVoltage.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `BatteryVoltage_Init1`
- `BatteryVoltage_Per1`
- `BatteryVoltage_Per2`
- `BatteryVoltage_SCom_ClearTransOvData`
- `BatteryVoltage_SCom_ReadTransOvData`


**Notable header dependencies:** `Ap_BatteryVoltage_Cfg.h`, `BatteryVoltage_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Os.h`, `Rte_Ap_BatteryVoltage.h`, `adc_regs.h`, `fixmath.h`

## Documents

- [Battery Voltage Module Design Document](documents/battery-voltage-mdd) — converted from `BatteryVoltage/doc/Battery_Voltage_MDD.doc`
- [BatteryVoltage Integration Manual](documents/batteryvoltage-integration-manual) — converted from `BatteryVoltage/doc/BatteryVoltage_Integration_Manual.docx`

## Repository location

All files live under `BatteryVoltage/` at the repository root.
