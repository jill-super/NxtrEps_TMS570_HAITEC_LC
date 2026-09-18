---
title: "Thermal Duty Cycle Management (ThrmDutyCycle)"
description: "Thermal Duty Cycle Management: purpose, files, interfaces and documents."
---

<div class="origin-badges">
  <span class="origin-badge origin-custom">Custom — in-house</span>
</div>
## Purpose

This module computes a duty cycle limit based on system temperatures.  It also outputs a unity scalar value to scale the assist command and a value representing the percentage of reduction.

:::note[Origin: Custom — in-house]
Nexteer Automotive copyright header. This is in-house developed code: it was written for this steering program and is fully documented here. It builds on top of the Vector MICROSAR Basic Software and the Runtime Environment.
:::

## Key files

| File | Role |
| --- | --- |
| `ThrmDutyCycle/src/Ap_ThrmlDutyCycle.c` | implementation |

The component ships AUTOSAR descriptions (`autosar/`: software-component templates, data types and port interfaces) used by the DaVinci/GENy tooling to generate the Runtime Environment.

## Interfaces and dependencies

**Entry points and runnables** (from the implementation):

- `StepVarXY_u16_s16Xu16Y_Cnt`
- `ThrmlDutyCycle_Init1`
- `ThrmlDutyCycle_Per1`


**Notable header dependencies:** `Ap_ThrmlDutyCycle_Cfg.h`, `CalConstants.h`, `GlobalMacro.h`, `MemMap.h`, `Rte_Ap_ThrmlDutyCycle.h`, `filters.h`, `fixmath.h`, `interpolation.h`, `math.h`

## Documents

- [Thermal Duty Cycle Module Design Document](documents/thermal-duty-cycle-mdd) — converted from `ThrmDutyCycle/doc/Thermal_Duty_Cycle_MDD.docx`
- [ThermalDutyCycle Integration Manual](documents/thermaldutycycle-integration-manual) — converted from `ThrmDutyCycle/doc/ThermalDutyCycle_Integration_Manual.docx`

## Repository location

All files live under `ThrmDutyCycle/` at the repository root.
